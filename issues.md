
# Issues

Fixed issues in fixed.md

## Issues

🟡 Delegated admin, IPAM - Bug related to looking up resources at different levels of hierarchy

🟡 ec2 instances, remaining roles - have to get past role assumption issue to test this.

## Add

🟡  Pentest jobs 

🟡  VPN

🟡  Yubikey Auth

🟡 Log Bucket >> Cloudwatch org logs? 
## Later

🟡 should be reporting scp output when blocked by scp is not

🟡 With profile fixes can probably deploy accounts in parallel now after handing off to parallel processor. TBD

🟡 Need to fix SCP for manage kiro to allow identity center + kiro for that account only. All other accounts blocked from kiro. Fix SCP

🟡 S3 cloudwatch logging > CloudWatch logs (new feature)

🟡 Nested OUs

🟡 Move an OU (align with a config change)

🟡 An account (align with a config change)

🟡 Resource specific actions - need to figure out how to handle these

🟡 Backup env should create a backup account for each env (confirmed by user), kms, iam

🟡 rename org 

🟡 rename env 

🟡 rename account 

🟡 rename a resource

🟡 Remove confirm mode

🟡 Seeing high route53 costs need to look into why that is. Check - need to query all DNS services and make sure DNS is locked down to only allowed accounts.

https://github.com/2ndSightLab/ai-tracker/blob/main/troubleshooting/route-53-costs.md

🟡 As per usual it messed up the DNS. It was only supposed to copy records except NS records and it update the NS records so I told it to fix that and fix and validate any incorret records at the time of the move.

🟡 Move hosted zone didn't update existing hosted zone so now the correct NS records are in one acount and the domain is associated ot the one with the wrong NS records I think not sure what is going on figure out tomororw.

🟡 Need a way to handle dup hostd zones in account 

🟡 Delete hosted zone didn't work becuase need to delete child records first.

🟡 close an account - ask if user wants to change name, email, alias so account can be recreated with same values

🟡 Review and fix KMS key policies, bucket policies, SCPs, iam policies, etc. etc. etc.



