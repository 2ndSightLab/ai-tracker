
# Issues

Fixed issues in fixed.md

## Issues

🟡 If account fails to deploy should not be looking up account resources and deploying them.

🟡 In Progress: Error messages should include file name and line number (wrote requirememnts, no project have yet picked up and implemented correctly.)

🟡 Errors getting logged when there are no errors - is it inadvertanly calling error logger instead of success logger? > tracked this down to incorrect error logging for org resources - to fix.

```
🟡 org: savisec (xxxxxxxx)
|
|     All Errors (every level):
|     |____ 🔴 savisec (error)
|           ↳ ERROR: botz-tracker-diagram: no error message recorded
|     |____ 🔴 organization (error)
|           ↳ ERROR: botz-tracker-diagram: no error message recorded
|     |____ 🔴 scp-deny-leave-org (error)
|           ↳ ERROR: botz-tracker-diagram: no error message recorded
|     |____ 🔴 scp-allowed-regions (error)
|           ↳ ERROR: botz-tracker-diagram: no error message recorded
|     |____ 🔴 savisec (error)
|           ↳ ERROR: botz-tracker-diagram: no error message recorded
|     |____ 🔴 account (error)
```

🟡 Make sure there is a timeout on waiting for depedencies.

🟡 Not correctly looking up already deployed account

🟡 account group header should be green when deployed, heading yellow if some reasons not deployed

## Later

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

🟡  Review and fix KMS key policies, bucket policies, SCPs, iam policies, etc. etc. etc.



