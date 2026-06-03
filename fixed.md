# Fixed Issues

6/3/2026 

 Removed ~230, added ~220. Net: ~-10 lines.

🟢 Still working...3:24 am menu code is royally messed up. so much duplication. I strated asking Google aimode how to fix it and does it SO MUCH FASTER. Gve it to Opus and I think it made opus go faster though Google AI mode code didn't follow my rules and hides a lot of errors. I've used 11% of $200 plan and feels like most of that was on stupid menus.

 
6/2/2026 6:18 PM - started with opus 4.6 but switched to 4.8 because it was makign mistakes. had to tell it to stop beign so verbose.

🟢 Menu is still messed up. model struggles with abstraction and no dup code.

🟢 Fix check for dup security group

🟢 Add option to go back to select ou menu and deploy/delete/verify menu. Ok for this one model made a complete mess of the menus and did not use the reusalbel menu code. what a mess.

🟢 Pull admin ips from other configs if exist keep having to look thos up, also admin acct, email domain, etc. maybe have a default configuration file

🟢 Add a verfication step for KMS policies - added output to kms verification

🟢 Job lambdas were incorrectly in management OU. Added to a new job step deploy job lambdas as an optional step if environmet type = jobs.

🟢 Delete should show resources in reverse order as last things deployed get deleted first due to dependencies; bug - ddin't properly align selection numbers with new step numbers.

🟢 Delete lambdas wasn't listing ALL lambdas for review

🟢 Quiet option for role ssumption to make output easier to read but leave the option for detailed troubleshooting; 4 tries still not working

🟢 Previously told model to move all the auth related stuff to a new account and it did not move the related networking. fixed. hopefully. 

🟢 Fixed VPC cost calcaultion bug / syntax error - not sure how it go there as I didn't think i cahnged the code in the VPC project. Hmm.

🟢 Kiro verification step doesn't display all settings. By the way I cannot change the URL but I 100% changed the url in the past somehow or the model wrote code that could do that somhow. Not sure how that happened because now all models are saying it is not possible ??/

🟢 Fixed some menu defaults that were missing after menu refactor. There are more...need to find them all.

🟢 Root SCPs only run in mangaement account and attached to root ou; env scps run in every environent and attached to env ou

🟢 Code reduction: After reviewign and fixing issues with IPAM/EIP code:

- Added: ~95 lines (new files)
- Removed: ~208 lines (XML boilerplate)
  
⭐️ Net: Removed ~-113 lines

🟢 EIPs were not being deleted in the correct account. had to tell it to look up which accounts had eips to release/delete.

🟢 IPAM fix did not work. Got it on second try easily.

🟢 IPAM updates were messed up at some point when I added the verification of each step. These shoudl be two searpate blocks of code. First of all the code was incorrectly changed to the xml file as just noted. Secondly, the model is confused because the IPAM pools are in the IPAM account but the EIP is alloated and registered in the account using the EIP - and if the model is cnofused may be the design needs a look. This is all confusing and I would have put the EIP in the IPAM account and used RAM share to share it out to an account. So there's a wish...

🟢 XML loading was all messed up and intertwined wiht another file in a way that made it possible to correct the execution order of loading and prompting. Created a load xml file instead and pull the junk out of the file that had diffenre stuff interwined all together like prompting, validation, and display configuration. A real mess actually.

🟢 The code was incorrectly pulling data from an XML file when requiremetns and i have told it over and over to never do that. Only query AWS. XMl is for inventory tracking at end of run only. adding additional reuqiremetns nda comments in files that were doing that and fixing it.

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
/usr/local/share/-projects/-env-bootstrap/config/env/x.xml:1: parser error : Specification mandates value for attribute ...arser error : expected '>'

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

