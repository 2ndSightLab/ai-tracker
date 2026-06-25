
# Issues

Fixed issues in fixed.md

🟡 Root SCPs - Bootstrap role perm - attach

🟡 Seeing high route53 costs need to look into why that is. Check - need to query all DNS services and make sure DNS is locked down to only allowed accounts.

# AWS Route 53 Cost Optimization Guide

If your Route 53 bill is higher than expected, it is rarely due to the flat $0.50 monthly fee per hosted zone. High Route 53 bills are almost always caused by high DNS query volumes, advanced routing rules, or active hybrid network endpoints.

Review your AWS Billing Console to see which of the following hidden cost drivers is spiking your bill:

### 1. High DNS Query Volume & Low TTLs
AWS charges $0.40 per million standard DNS queries. If your application gets a surge of traffic, your query costs will jump.

* **The Problem:** If your DNS records have a very low TTL (Time to Live), like 60 seconds, external browsers and DNS resolvers cannot cache your domain. They are forced to ping Route 53 constantly for every single user request, driving up your query count.
* **The Fix:** Increase your TTL values to 300 seconds (5 minutes) or 3600 seconds (1 hour) for records that do not change frequently. This forces browsers to cache the answer and stops them from constantly billing you for lookups.

### 2. Using CNAME Records Instead of Free Alias Records
If you point your domain names to other AWS resources using standard CNAME records, you pay for every single DNS lookup.

* **The Fix:** Switch your records from CNAME to Alias records. Queries to Alias records are completely free if they point to qualifying AWS resources like CloudFront distributions, Elastic Load Balancers (ALB/NLB), API Gateways, or S3 website buckets.

### 3. Expensive Route 53 Resolver Endpoints (Hybrid Cloud)
Did you set up a Route 53 Resolver Endpoint to connect your AWS cloud environment to an on-premises office network?

* **The Problem:** Resolver Endpoints require Elastic Network Interfaces (ENIs) which cost a steep $0.125 per hour each. Because high availability requires a minimum of two endpoints, a single active Resolver setup will cost you a fixed baseline of roughly $182.50 per month, entirely separate from your standard query volume.
* **The Fix:** If you do not actively pass traffic back and forth between a physical corporate server room and AWS, delete these Resolver endpoints immediately.

### 4. Over-Engineered Advanced Routing Policies
Standard queries cost $0.40 per million, but advanced routing costs significantly more:
* **Latency-Based Routing:** Costs $0.60 per million queries.
* **Geo-Location / Geo-Proximity Routing:** Costs $0.70 per million queries.
* **Traffic Flow Policies:** If you configured visual "Traffic Flow" maps to route users, AWS charges a flat $50.00 per month per policy record.
* **The Fix:** Unless you are managing a massive multi-region architecture that absolutely requires geo-targeting, revert your records to Simple Routing to lower your per-query costs.

### 5. "Zombie" Hosted Zones or Active Health Checks
* **Unused Zones:** Every domain zone you create charges $0.50/month. If you spin up test subdomains or temporary dev environments and forget to delete them, those fees add up silently.
* **Health Checks:** Monitoring non-AWS endpoints costs $0.75 per health check per month. If you have dozens of automated health checks pinging external servers every 10 seconds, it will bloat your bill.

---

## How to Check for Active Hybrid Network Endpoints

You can easily check for active hybrid network endpoints (officially called Route 53 Resolver Endpoints) directly in the AWS Console. Since these endpoints are region-specific, you need to look at the regions where your primary infrastructure or VPCs are running.

### Step 1: Open the Route 53 Resolver Console
1. Log in to the AWS Management Console.
2. In the top search bar, type **Route 53** and select it.
3. On the left-hand navigation pane, scroll down to the **Resolver** section.
4. Click on **Inbound endpoints** or **Outbound endpoints**.

### Step 2: Check Your Active Regions
1. Look at the main table in the console.
2. **Crucial:** Look at the top-right corner of your AWS console to see your current Region (e.g., N. Virginia, Oregon, Ireland).
3. Use the Region selector dropdown to switch between any regions where you have active resources or default VPCs configured.

**What You Are Looking For:**
* **If the tables are empty:** You do not have any hybrid Resolver Endpoints active in that region. They are not the cause of your high bill.
* **If you see endpoints listed:** You will see a table showing an endpoint name, its status (`OPERATIONAL`), and the specific VPC ID it is attached to.

### How to Delete Them to Stop the Charges
If you find active Inbound or Outbound endpoints that you do not need, you can delete them to stop the $0.125/hour per ENI baseline fee immediately:
1. Select the radio button next to the active endpoint.
2. Click the **Delete** button at the top of the table.

> **Note:** If you have active Rules associated with an outbound endpoint, the console will prompt you to delete or disassociate those forwarding rules first before it allows you to delete the endpoint itself.

🟡 As per usual it messed up the DNS. It was only supposed to copy records except NS records and it update the NS records so I told it to fix that and fix and validate any incorret records at the time of the move.

🟡 Move hosted zone didn't update existing hosted zone so now the correct NS records are in one acount and the domain is associated ot the one with the wrong NS records I think not sure what is going on figure out tomororw.

🟡 Need a way to handle dup hostd zones in account 

🟡 Delete hosted zone didn't work becuase need to delete child records first.

🟡 Ram sharing worked for one VPC but it's not working for the other three nad the models are going aroudn and around in circles and cannot figure it out.

🟡 Rename and account - name, email, alias - use this before closing an account

🟡 Close account is not working and before closing an account need to fix the following: change alias name, change account name, change email address - to avoid conflicts if need to recreate the account.

🟡 The KMS key polic is too broad - allows access to any key and is applying it to eevery lamda in ou. I have an SCP to block that but still annoying. I need to review all the policies in detail later and will use the IAM access analyzer plus manual review. I don't think IAM access analyzer handles resource policies but prowler will to a degree.

🟡 Deploy resources concurrently where possible; my initial attempt to ask this quetion got really convoluted sugestions.
