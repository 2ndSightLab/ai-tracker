# Fixed Issues

6/4/2026 9:03 PM Going to give automode another chance

🟢 Previously I asked it to rename an instance step and it also renamed a file to match the step I didn't ask it to change that references a file in another project. That caused me to scratch my head for a while until I figured it out. There was no file not found error or configuration confirmation so I added that.

🟢 This is from a prior update. Why does th emodel alwasy put so many ../../../tmp instead of just /tmp?

6/4/2026 2:27 Let's go. Unlocking and logging in.

🟢 Ensure the bucket deploy lambda is deployed to every account to deploy the log buckets. I had to spend a lot of time gettng the model to do this in a way that would result in good code.

⭐️ Net Lines removed: 44

🟢 OMG. I just go through telling it to fix the coode to lop through every acount in the OU and deploy log bucket. The deployment got an error. It's now trying to undo the code and only deploy those bucekts in certain acounts agian. I literally just had it fix that.

🟢 Verify is running when nothing has changed. And now the model is trying to add a zillion more lines of code with a new variable. It can't figure out what it doesn't need a ew variable. There's an existing varaible other steps aren't using and it's set to "" at teh begining of each step. So if you try to use "" to eval that nothing was changed verfiy will skip for all those other steps. To skip verify just chagne that existing variable to 0 if teh step was skipped. The other steps will see "" and continue to verify but if it's 0 verify is skipped. The model can't figure that out. It want's to create new stking variables for everything which is why the code is litterled with 15 million extral lines it does not need. I exaggerate for emphsis. Only slighly exaggerated. Argh.

🟢 Found yet another inconsistent menu. 

🟢 Keep getting asked for verification code over and over in lambda vpc config step. Once again the project tries to get me to change the role assumption code which has been workign for months. Move your security code to a separate project. The problem had nothing to do with the other project. the reason i was seeing the request multple times is because the code failed to say what resource it was deploying before it did each one. Which is in the requirements.

🟢 If a concurrency error occurs don't keep trying to deploy in that acocunt. Show the comand to run then skip to the next account after the user chooses to continue.

🟢 After waiting a bit and doing other things deploy lambda after concurrrency quota request. Nope. I have no idea how long to wait.

🟢 Removing all the widgets I don't want to run every time I open my account as I log into new accounts.

🟢 On that note, because I cannot define the password when I create a new account and I can't do something liek use and existing RAM shared admin MFA or something I have to log into each acocunt in the OU and go through the password reset step. Yes I know I can disable the root admin but that's a pain. I do not create users in every account. I creat them in one IAM acocunt. To get to the other account  have to log into the IAM account and use the user I created to asume a role to get to an account and my users don't have all powerful privildges. I like to have the option still to get in as root. Yes I know you cna diable root everywhere. I know. But assuming a role is painful sometimes compred to just logging in. I may revisit the whole lock down the root account thing later when my scripts are 100% relaible. But I stll think I'd like to set hte MFA on them in case I need to undo that access and get in with the admin befoer I lock them down. IDK need to look at it. Just let me set a passord when I create teh acocunt.

🟢 Have to change lambda concurrency in mroe accounts. I can't remember why but ther was a reason I couldn't autoamte this so I have to login to teh acount and run a script I output in an eror message to make that request.

🟢 If prompt has ? at end do not add : like Change creds?:

🟢 Another menu is not consistent.

⭐️ Lines added: 321 Lines removed: 70 Net: +251

⭐️ So approximately 120-130 distinct lines were edited more than once, with the error blocks and the SKIPMENUS loop being
the most-rechurned. That rework is wasted token/effort churn — most of it from me adding step-error-menu.sh and the 
SKIPMENUS approaches before settling on the final version.

🟢 Tried to add unneccesary files again to deploy additional log buckets. WHY? just loop over the accounts and call create-bucket.sh. Had to walk the agent through that.

🟢 Log buckets missing.

🟢 old configuration menu after steps is inconsistent even though I told it to make sure has the same menu after every step.

🟢 Redeploying the role when nothing has changed - in every account.

🟢 Spending WAYYY to long just trying to deploy a lambda funciton. (Correctly wihtout generating garbage slop code).

🟢 Error in archive lambda related to kms keys; such covolutedness trying to sovle that. Everything always about KMS keys policies and permissions is always convolutedness so no wonder the model can't figure it out. After reewing the policy, logging an issues and coming back to the original problem after telling it to forget all the plicy isues, it magically quickly fixed the code to deploy the policy in very few lines and is suposedly assuming a role it told me didn't exist a minute ago. Let's see if it works now.

🟢 I'm at 27% usage right now and all this rework is burning tokens.

🟢 It did not listen to me when I told it to use teh extraneous menu and use the shared menu adn was changing a whole boatload fo code in multiple places for some unknown reason. Now it has to go back and un-mess up all the places where it added the wrong menu file.

🟢 So now I see that it has added an uneccessary new menu file when the current menu file would suffice with almost no tweaks.

🟢 The menu is wrong again. Instead of fixing repeat curent step it added the name of the current step to the top of the menu which is redundant. I told it to leave the name and remove the repeat step as that is fine and to update the readme - AGAIN. It failed to update the readme last time with the missting information. Then after I asked it to do that apparetly number 1 never worked at all so it's spinning it's wheels fixing a whole bunch of code right now and probably breaking something else.

🟢 After deloying archive lambda which is another project and worked it throws a resource already exists error. I keep telling it not to prduce errors and duplicate code. The existence can be checked without generating an error and that is an incorrect result. Errors should be generated when theare are ACTUALLY ERRORS.

🟢 After filtering a list if there is only one item make it teh default.

🟢 unbound variable after updateing role code in archive lambda. That happens way too much. I ahve a rule to prevent it but agents don't follow the rules half the time.

🟢 switched from 4.6 to 4.8 in bootstrap project

🟢 And... while trying to fix that did to much and broken even mroe code.

🟢 And....it broke a working menu so fixing that again.

🟢 archive lambda didn't use the shared assume role code was doing it's own thing. GEEZ. It spun it's wheesl forever on something so dang simple. I had to stop it multple times. Told it to follow the patterin gin the bootstrap role. It didn't. I told it what file to look at it did it wrong. I gave it the code and said create a wrapper script (which is like the bootstarp project and is like 6 lines of code). It copied all the code out ouf the shared role assumption file. I told it to delete that file and create a file with exactly the code I gave it and what to name it and in about 3 lines of additional output it was done. It's like it's intentionally trying to get control of the role assumption code and mess it up. I know the model itself has no intentions but what was it trained on that causes it to do that? It meses up role asumption a LOT and tries to duplicate it rather than use shared code. (implemented that yesterday testing now)

🟢 Fix the menu after every error message to be consistent to use the common step completion menu so I don't have to keep exiting the program and startin gover when something goes wrong.

🟢 Had to quit session and start over because I started a new request and was mixing up with the prior request. 

🟢 Failed to follow rules again. Had to remind it by asking "Are you following the rules?"

🟢 Add to global prompt to always show me the ui and ask for approval before changing; don't write what you see just waht you are going to do or have done. Also need to add model selection option to upate agents in my framework.

🟢 found more incorrect menus and model is struggling to update them correctly

6/3/2026 

🟢 AI models are bad at reusable, clean menu code.

🟢 Super annoying !!! I think the models get dumber in the middle of the night. I have explicit file names in readme. The model just started adding a bunch of extraneos fiesl - ddeploy-single-bucket, deploy-bucket-iwth-kms blah blah blah. I spent a lot of time steamlining that in the past nad it jsut screwed it all up and ducliated a bunch fo code. FFFFFANNOYING. I told it to read the reuqiremetns agin. The code is probably a mess again. This is why you can't trust AI. Have to watch it all the time.

🟢 Every time I start deploying Lambdas in a new account I get this and have to fix it.

  Existing quota increase requests:
    Status: CASE_OPENED  Desired: 1000.0  Created: 2026-06-04T08:09:07.522000+00:00

  To request 1000 concurrent executions, run in CloudShell:...

🟢 After some change double promted to deploy things

🟢 Added Previous step like next step

🟢 Model really strugges with UI consisteny. In the move domain step it put the header for the next step above the list of items including an option to run the next step.

🟢 Register domain step

🟢 Run IAM Access analyzer Step - per ou or in entire organization 

🟢 Used Google AI mode to simplify main menu.

⭐️ 18 lines removed.

🟢 Add backup vpc for archive acount lambda

🟢 why is this empty stuff in the configuration
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
🟢 O: review code and reduce redundant code

🟢 y/n/e probable needs an m (main) and environment action (a) option to go back to the main menu y/n/m/a/e (implemented anotehr way)

🟢 archive lambda needs cross account permissions to read any resource it needs to back up in any account in the OU 

🟢 step for selecting which resources to deploy instead of just deploying "all" - deploy all or select numbers, shared menu that can be used for all resources.

🟢 Need archive vpc that can be deployed if needed and torn down when done archiving to save money (vpc endpoints especially) + remove the role?

🟢 archive lambda needs cross account permissions to read any resource it needs to back up in any account in the OU

🟢 Remove more dead code

⭐️ 98 more lines of dead code

🟢 Duplicate sg verify for every sg 

⭐️ 49 lines removed

🟢 Remove dead code realted to teardown function that was revised to use a per resource deletion scipts but the model never removed the dead code.

⭐️ 3,703 lines of dead code.

🟢 Move archive lambda and role into it's own step. - forgetting where to put this. It goes in teh backup account because that account needs to pull stuff into it. Also that lambda needs cross account permissions to read any resource it needs to back up in any account in the OU (to reivew later).

🟢 Remove duplicate code in delegated administrator code.

⭐️ ~320 lines removed.

🟢 I have a rule to never use temp files and yet the code is writing a multitude of temp files in teh config directory creating a humongous mess. I told the agent to make every piece of code that is writing a temp file to clean up after itself rather than try to fix this all at once and break everything. Those temp files are wasting resources if the model is reading them. Super annoying.


🟢 Added transfer domain step sing soe code I wrote before. I inadvertantly closed an account with some doains and had to get AWS to restore the account. Now I nee to use that step to transfer those domaisn into a new OU.

🟢 Redeloy single VPC wasn't working right

🟢 Security groups - prefix list not found

🟢 Auth VPC incorrectly named web vpc when switched accounts

⭐️ Removed ~230, added ~220. Net: ~-10 lines.

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

⭐️ Lines removed: 115

🟢 Backup account is missing from accounts list in non-management verficiation step. 

🟢 Backup account is missing from accounts list in management account verficiation step.

🟢 request what env type up front - management, jobs, web, test, other and display corresponding list of resources to deploy

