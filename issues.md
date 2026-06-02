
# Issues

🟡 For me to fix  🟢 Resolved

6/2/2026 6:18 PM 

6/1/2026 - 6/2/2026

🟡 Make sure VPC endpoints are optional and not configured eveywhere until confirm everything else is working properly to reduce costs excpet possibly the auth Lambda.

🟡 Close account is not working and before closing an account need to fix the following: change alias name, change account name, change email address - to avoid conflicts if need to recreate the account.

🟡 Currently I choose a region per env and I may allow different environments to operate in different regions but have no support for that. SCP allowed-regions [root] needs to only be deployed with management environment and allow global regions. Then an SCP per environment or account can optionally further restrict access.

🟡 Issue with role assumption - until the org admin role is created need to use the AWS default role with no MFA. Once created, the AWS Org role needs to be disabled with an SCP (presuming it is not a service-linked role which is not subject to SCPs). I need to #1. Verify it is deployed as a non-SLR #2 Create the SCP #3 Depploy it at the appopriate point #4 maybe have an undeploy step run to remove it if needed

🟡 Lists need a Return to Main Menu and return to Environment Action menu option before Exit

🟡 y/n/e probable needs an m (main) and environment action (a) option to go back to the main menu y/n/m/a/e


🟡 Pull admin ips from other configs if exist keep having to look thos up, also admin acct, email domain, etc. maybe have a default configuration file

🟡 Delete should show resources in reverse order as last things deployed get deleted first due to dependencies

🟡 Rename and account - name, email, alias - use this before closing an account

🟡 add a help function for all configuration items - type h and it writes the info then prompts again

🟡 Clarify what the domain names are for in the prompts for env config - do i need the org domain in all cases? 

🟡 review code and reduce redundant code

🟡 Info missing kiro instance: Not sure this is really my bug. After programmatically creating Kiro profile in acount it's all blank. It wasn't this way before so I think some thing at AWS cahnged. Need to revisit and test adding and removing Kiro but it ssems to be working with that last manual step. I had documented that I had to manually take that last step in the program so maybe that's the way it is.
```
Name
-
Description
-
AWS Organizations account type
Individual
Profile ARN
-
IAM Identity Center region
-
Sign in URL
-
Users & Groups
-
```

🟡 why is this empty stuff in the configuration
```
  --- us-east-1 ---
  CONFIG_BUCKET: not set
  LOGS_BUCKET: not set
  JOBS_BUCKET: not set
  VPC: not set
  KMS_ALIAS_LOGS: not set
  KMS_ALIAS_CONFIG: not set
  KMS_ALIAS_AUTH: not set
  KMS_ALIAS_JOBS: not set
```
🟡 Adding object logs to CloudTrail is expensive. Todo: Try this hack I got out of Google aimode:

1. Enable Free S3 Server Access LogsS3 Server Access Logs are completely free to generate.Create a dedicated log destination bucket (e.g., my-s3-logs-bucket).Turn on Server Access Logging on your primary data bucket and point the destination to your log bucket.2. Deploy a Lambda "Log Processor"Create an AWS Lambda function triggered by an S3 Event Notification whenever a new log object is created in your log bucket.Because S3 writes logs in batches every few minutes, Lambda only triggers a few times an hour—not on every single file download. This keeps compute costs incredibly low.3. Write a Python script to filter and uploadUse a Python script inside your Lambda function to compress, filter out unneeded traffic, and send only the important data to CloudWatch using boto3.Below is a complete, production-ready Lambda function to handle this pipeline:pythonimport boto3
```
import gzip
import re

s3_client = boto3.client('s3')
cw_client = boto3.client('logs')

# Change these to match your environment
LOG_GROUP_NAME = '/aws/s3/custom-object-access'
LOG_STREAM_NAME = 's3-access-stream'

def lambda_handler(event, context):
    # Ensure the CloudWatch log stream exists
    try:
        cw_client.create_log_stream(logGroupName=LOG_GROUP_NAME, logStreamName=LOG_STREAM_NAME)
    except cw_client.exceptions.ResourceAlreadyExistsException:
        pass

    # Extract bucket and file name from the S3 event trigger
    bucket = event['Records'][0]['s3']['bucket']['name']
    key = event['Records'][0]['s3']['object']['key']
    
    # Download the log file from S3
    response = s3_client.get_object(Bucket=bucket, Key=key)
    log_data = response['Body'].read()
    
    # Decompress if S3 automatically gzipped it
    if key.endswith('.gz'):
        log_data = gzip.decompress(log_data)
        
    log_lines = log_data.decode('utf-8').splitlines()
    
    log_events = []
    
    # Regex pattern to parse standard S3 Server Access Log format
    log_pattern = re.compile(
        r'(?P<owner>\S+) (?P<bucket>\S+) \[(?P<time>[^\]]+)\] (?P<ip>\S+) '
        r'(?P<requester>\S+) (?P<req_id>\S+) (?P<operation>\S+) (?P<key>\S+) '
        r'"(?P<request>[^"]*)" (?P<status>\d+) (?P<error>\S+) (?P<bytes>\S+)'
    )
    
    for line in log_lines:
        match = log_pattern.match(line)
        if match:
            data = match.groupdict()
            
            # --- COST SAVING FILTER ---
            # Example: Only send DELETE or PUT operations to CloudWatch, ignore GETs
            if data['operation'] not in ['REST.PUT.OBJECT', 'REST.DELETE.OBJECT']:
                continue
                
            # If it passes the filter, format for CloudWatch
            import time
            # Fallback to current time if log timestamp parsing is omitted for simplicity
            timestamp_ms = int(time.time() * 1000) 
            
            log_events.append({
                'timestamp': timestamp_ms,
                'message': f"User: {data['requester']} | Op: {data['operation']} | File: {data['key']} | IP: {data['ip']}"
            })
            
    # Batch upload to CloudWatch if any matching logs were found
    if log_events:
        # CloudWatch limits batch uploads to 10,000 events at a time
        for i in range(0, len(log_events), 10000):
            cw_client.put_log_events(
                logGroupName=LOG_GROUP_NAME,
                logStreamName=LOG_STREAM_NAME,
                logEvents=log_events[i:i+10000]
            )
            
    return {"statusCode": 200, "body": "Logs processed successfully"}
```
4. Apply a Strict Cost FilterThe main code logic that saves money is the Cost Saving Filter block in the code above.The Secret: CloudWatch still charges $0.50 per GB for data ingestion [1].If you forward every single read/write line from S3 to CloudWatch, you will still run up a high CloudWatch bill.Use the Lambda code to discard GET or HEAD operations. Only forward high-importance actions like DELETE or PUT, or actions originating from unauthorized IP addresses.Summary: CloudTrail vs. S3+Lambda ArchitectureMetricCloudTrail ApproachS3 + Lambda ApproachAWS Event Fee$0.10 per 100k events [1]$0.00 (Completely Free)Ingestion FeeFull price on every byte logged [1]Massively reduced via Lambda filtersSpeedNear real-time (1–3 mins)Slightly batched (5–10 mins delay)



