
# Issues

Fixed issues in fixed.md

## Issues

🟡 Keep running out of credits and is stopping me. Usage based credits cost more. If I am goign to use those probably want to use those through AWS so I can track the cost. So combined with figuring out how to use Fable I want to have an alternative when my credits run out. I tried Claude but it doesn't work the way I want as logged under mistakes. I wish I could use Kiro only but so far Claude is lasting longer, but with timeouts. So with the timeouts is it really less expensive? What if I switch to the $200 plan because in theor then I get even more tokens/credits. Hmm.

🟡 Cannot use Fable in Claude with a subscription. Need to figure out how to set up API key or usage based access to use Fable. Possibly billed through AWS or test billed through AWS and not through AWS to see if there is any difference.

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

🟡 Figure out why projects are not reading configuration file projects and aligning to them > architecture not clear enough?

🟡 Go through every resource project and tell it to fix error handling. If errors are clear fixes should be easier.

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



