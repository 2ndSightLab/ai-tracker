
🟡 For me to fix  🟢 Resolved

6/1/2026

🟡 Make sure VPC endpoints are optional and not configured eveywhere until confirm everything else is working properly to reduce costs excpet possibly the auth Lambda.

🟡 UI: Step completion prompt is inconsistent. Sometimes has Quit and Exit. 

🟡 Close account is not working and before closing an account need to fix the following: change alias name, change account name, change email address - to avoid conflicts if need to recreate the account.

🟡 Backup account is missing from accounts list in non-management verficiation step. 

🟡 Backup account is missing from accounts list in management account verficiation step.

🟡 Currently I choose a region per env and I may allow different environments to operate in different regions but have no support for that. SCP allowed-regions [root] needs to only be deployed with management environment and allow global regions. Then an SCP per environment or account can optionally further restrict access.

🟡 Issue with role assumption - until the org admin role is created need to use the AWS default role with no MFA. Once created, the AWS Org role needs to be disabled with an SCP (presuming it is not a service-linked role which is not subject to SCPs). I need to #1. Verify it is deployed as a non-SLR #2 Create the SCP #3 Depploy it at the appopriate point #4 maybe have an undeploy step run to remove it if needed

🟡 Lists need a Return to Main Menu and return to Environment Action menu option before Exit

🟡 y/n/e probable needs an m (main) and environment action (a) option to go back to the main menu y/n/m/a/e

