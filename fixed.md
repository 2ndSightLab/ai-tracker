# Fixed Issues

6/2/2026 6:18 PM 

🟢  Asked to create SCP that disallows IMDSv1. Athropic model only provided 2 of 3 required policy compnents. Google aimode provided all three.

🟢  The coee to skip env prompt when env was selected and save to file on prior run not working.

6/1/2026 - 6/2/2026

🟢  Stuck in all directions and connot test any further until I fix the following. What I have to do now is re-set up my Kiro environment or use an account temporarily in my old environment until I fix and deploy Kiro in the new environment. Since I deleted my old instances and AWS Identity center I'm going to set up a temp OU and account for this purpose
Fix: was able to deploy Identity Center and Kiro in new environment even though other stuff was blocked. Had to figure ou why the profile was blank and what to do about that. Had to enteer a user email to enable kiro which was not my logged in user or a user I had given ANY permissions to so that was weird.

🟢 Was not checking for log bucket existence before assigning log bucket to a bucket

🟢 Added verification bucket lambda exists beore deploying buckets - this is the problem with using lambdas vs. just using the script with the CLI

🟢 Deploy budgets works but verify budgets deletes the budget it is supposed to be verifying.

🟢 Adding bucket logging somehow broke bucket deployments.

🟢 AI Bug
[us-east-2]
/usr/local/share/botz-projects/botz-env-bootstrap/config/env/x.xml:1: parser error : Specification mandates value for attribute ...arser error : expected '>'

🟢 AI Bug - rules say to use xmllint and it used python

🟢 Cannot deploy specific accounts. it's giving an error saying required accounts are not deployed. Also shoudl be able to deploy an account with whatever name. Requirement accounts depend on environment type.
- Added custom option for environment type allowing any account list - in theory only resources for selected accounts will be deployed but this needs to be tested.

🟢 AI Bug -  line 38: ENV_TYPE: unbound variable

🟢 Deafult to what is in XML if set - Environment type:
  1. Management (organization management OU)
  2. Jobs (standard multi-account)
  3. Custom (choose accounts)
  4. Exit

🟢 UI: Step completion prompt is inconsistent. Sometimes has Quit and Exit. > removed quit - found a large list of menus not using the shared menu file and fixed.

⭐️⭐️⭐️ Lines removed: 115 ⭐️⭐️⭐️ 

🟢 Backup account is missing from accounts list in non-management verficiation step. 

🟢 Backup account is missing from accounts list in management account verficiation step.

🟢 request what env type up front - management, jobs, web, test, other and display corresponding list of resources to deploy

