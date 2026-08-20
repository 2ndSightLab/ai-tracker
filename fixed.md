# Fixed Issues

Typos cuz these are just notes for me... 

The way I'm ordering this is weird sorry. I write the date/time and stuff I did between the two dates and times is bottom up. Probably should do it dff but just notes.

## 8/17/2026

🟢 Fixed: Cannot use Fable in Claude with a subscription. Figure out how I can try out Fable and see if it makes a difference without turning on usage-based billing for my subs which could lead to accidentally huge bills. - Fable showed up when I upgraded my plan.

🟢 Fixed: Keep running out of credits and is stopping me. Figure out a plan for switching to another option when credits expire. Tried to use Codex. Model didnt work that great for my particular project and sandboxing doesn't work with my framework very well. So will not be Codex. I can be those models through Amazon Bedrock. I can also use Kiro. I can also set up accounts for Claude through AWS. - updated Claude plan for one user. Also then Fable showed up. When I tried to use Amazon Bedrock ran into some issues:

https://teriradichel.substack.com/p/cant-get-role-with-mfa-to-work-on

🟢 Clear tracker errors is still not correctly clearing errors.

## 8/16/2026

🟢 Only run failed items (supposedly fixed) > reverted logic that had to be fixed again in the deployment orchestrator.

🟢 Fixed error logging in run aws command and cli project.

🟢 Menu bug in run aws command project

🟢 account resource should be under the account heading - is missing and should have id associated with it

🟢 Projects still failing to review and correctly understand organization configuration - fixed again and logged mistakes.

🟢 Various errors re-introduced by orchestrator.

🟢 Remove XML from error files. Encoded error message ONLY.

🟢 Fixed: No errror are associated with the nodes anymore. Errors need to be logged to this path where IDs are the ids in the config not aws IDS.

🟢 Fixed: Success logging is not working. Success logging needs to be logged to this path where IDs are the ids in the config not aws IDS except for the value of the aws id in the file.

🟢 Fixed: For some reason now exiting instead of letting me re-enter a mfa code if i make a mistake.

🟢 Fixed: Turned off claude overwriting terminal tabs.

## 8/15/2026

🟢 OK I fixed the parallel processing issues related to role assumption with profiles that use short term creds. I fixed the problem with xml tracker file locking by writing success and error nodes to separate files and processing those queues in a single threaded queue processor. But one problem remains. Global vars can be clobbered while deploying multiple resources at the same time. So I spent the morning adding requiremtns to exec a file and pass in the NODE_PATH for a resource and teh exec wrapper runs in teh background in it's own process. It parses out the neccessary globals that can chagne from the path in it's own thread and sources the deployment script. That way the vars are local to the deployment action and should not get clobbered.

🟢 Another problem: error logging is writing useless error messages. The first step to solving that probelm is to include the file path and line number in the error so I added that requirement to the global readme. I need to do more but that's a start.

🟢 I wrote explicit instructions related to the node path and files in the architecture readme so those file paths and parsing out the aligned path in the diagram are explicitly defined and the process for adding ids and errors to the correct nodes is clearer.

🟢 I added explicit instructions to put the base64 encoded error message in the error file ONLY. 

🟢 Kicked off five agents to fix the related projects according to those instructions...running....but then i set only ONE project to ultrathink and IMMEDIATELY ran out of credits. In the past I had 2-3 projects running in ultrathink and this did not happen. I don't understand this at all.


## 8/14/2026

🟢 Fixed manually: Should not be logging errors when roles are not configured because they get configured in the process.

🟢 Finally parallel process is getting through all accounts and role assumption at all points is working correctly. No eternal loops and fixed a bunch of wonky errors.

🟢 Fixed an error that after some other "fix" by the model caused the diagram to completely hang. That took a while for the model to sort out and stop finger pointing between projects.

🟢 Fixed: Just realized that after "freezing" credits to prevent login issues, that role assumption is failing for both the mfa and no-mfa role on and account. AGAIN. Fix one and another appears. Will be manually revisiting that code tomorrow and cleaning it up. I think the solution is not to overwrite the account but to configure a temp role for the "frozen" credentials and just add a new role name to the mix. I'll need to sort that out when not so tired. 

Had to re-write what the model did again to have clean decent file names, abstraction, deduplicated and logical code. Fixed a logical flow issue that was preventing new account creation and role assumption.

🟢 Fixed: Some of the errors are still base64 encoded in the diagram they need to be converted to text when displayed. > this is partially fixed but not completely. Part of the problem is that the error logging is messed up as explained in mistakes section. TO DO.

🟢 Better: Diagram is better but still slow. It doesn't seem to load whene the app is running. (good enough for now)

🟢 I "fixed" something with the org admin role to remove the extranoues policy and now that role is not deploying and things are hung up that depend upon it, blocking everything.

🟢  Empty tracker error - why? No idea but gone after above fixes.

🟢 Make sure there are not too many children under deny exernal 

🟢  env yellow when nothing deployed in: Not sure if really fixed because every environment has something deployed in it...but no longer there.

## 8/13/2026

Objective today is to reduce the token burn and get the bugs fixed. I know what the bugs are and what caused them since they got reintroduced by migration. So why is the model spinning when trying to fix them? Claude is back so let's see what we can do.

🟢 While testing figured out that the projects were not all initialized with Claude.md file. New projects will be not existing. Created a script for that an ran it.

🟢 Eternal looping: I know what causes this. The role assumption is buried in a subshell. It needs to be pulled to the foreground becuase otherwise it hangs waiting for a code the user cannot enter. Well moving it to the foreground seems like the solution. It's what all the Anthroopic models have been claiming is the problem since I implemented the parallel processing. I told the model via Claude and Kiro before that repeatedly to fix it but it's still producing and reintroducing that problem after it was already fixed. I kept refereing to the old code but the models can fix it. So let's do a brute force trace of what files are causing the problem and be more explicity about telling the model how to fix it. I've got some tokens again for Claude so let's use that. To fix started by adding explicit instructions for the particular problem that keeps occuring...

So what is interesting here is that way back when I started writing about this cybersecurity automation framework which is essentially a way to run jobs which now can include agents...I was assuming roles and using static credentials with the roles to run batch jobs, because I was passing the creds around to allow the role to have short term credentials assumed on a separate compute resource (locked down with IP restrictions also). But in this iteration I was doing the normal role assumption not putting the short term creds in a role configuration.

I don't know how this worked before but I turned on ultrathink in claude and for the first time since I implemneted parallel processing it's telling me to assume the role and get the STS role creds and use those to "freeze" the role assumption. It's telling me that the role assumption cannot pass from the parent to the child process. HUH? That worked before I thought. But whatever fixes it. So assume a role, get short term creds, and use those to create a new role profile and use the role profile to carry out all the commands.

So it did that and messed up a bunch of stuff but finally got it working I think. 

I had also told claude to create tests for EVERYTHING. It failed to create tests or fix tests even though it was a requirement in the global requirements. The models do not work any better at reading the global requirements in Claude Code. In fact they seem to be skipping my logging instructions for the most part.

But anyway that is sort of resolved. But is it?

Digging through the logs. no it is not. I had it assuming a no-mfa role and if that fails assuem the mfa role (because initially the org role has no MFA). That was working. But something with the role was not working during parallel processing which I thought got fixed. But it did not.

Now for an account role neither is assumed. Great thanks. I'll probably fix that manually tomorrow as I think it won't be that hard to fix and the models just think forever and cannot solve it.

🟢 The diagram is improved, but still slow. I still have work to do there. But it works. I'm seeing a bunh of bugs I have to fix that weren't in the old code though.

## 8/12/2026

🟢 Set up my framework to work with Claude Code or Kiro (default). Wrote about some of the mistakes and issues using Claude Code to set that up in mistakes.md. Now I can use alias c to run claude code for a specific project or k to run kiro for a specific project. The tool runs with the specified linux user that has limited access to the specific project folder but can read the code in all the other projects on the system. How I plan to use this is to run the framework for different groups of projects on different systems to limit the amount of code an agent has to look at.

🟢 I spent most of the day manually fixing the role assumption issues because the agents just make a mess of that. I go to the very end and one thing was wonky. Claude figured out what it was kind of. I was choosing the wrong option at some point. I need to make that more clear, I think.

🟢 After a lot of thinking Claude correctly diagnosed that the migration of the code to the new project architecture failed to copy over some critical logic for organization wide resources. The migration was literally suposed to copy that code over and yet it mucked it up along with a bunch of other things I'm having to redo now, creating really complicated problems. Sorting them out one at a time but I feel like I shouldn't have to be doing this since the instructions were literally, copy the code. Only make changes required by the architecture README.md. This was not a required chagne. Super annoying. Oh but when it tried to implement it screwed it all up and didn't use the old code which creates a list of resources and gave it a stupid name "fan out" which is the new fangled word everyone uses for agents with claude and honestly it annoys me too. It's jsut supposed to put together a list of resource to deploy. There's no fan involved.


Just going through issues list and some stuff has been fixed:

🟢 Root SCPs - Bootstrap role perm - attach

🟢 after deploy IAM users wrong list of options - inconsistent

Select an action for admin users:
  1. Deploy admin users
  2. Done
  3. Exit

This is really n/a now.

🟢 Fix rename/menu issues

🟢 Deploy resources concurrently where possible; my initial attempt to ask this quetion got really convoluted sugestions. [working but a few bugs to sort out]

🟢 Wrong IP in admin user policy

🟢 Fix KMS key deployment - ERROR: deploy-kms-logs-key.sh is not implemented

🟢 When budget exists check to see that it is acutually replacing all existing budget amounts.
  Budget amount auto-set to $30 (highest threshold)
  x-org: budget exists ($50.0/month)
  Updated to $30/month
  Account Budget complete

  This was replaced with per account budgets. May need some additional testing but I think this is working.

## 8/11/2026

🟢 Framework is kind of running with bugs as noted elsewhere. Burned another $200.

## 8/9/2026

🟢 The project group configuration is now working and the architecture I defined to split the tracker into four sepraate projects worked. All new projects are created at agents are properly initialized.

🟢 Told the architecture project to review the existing code and formulate prompts for al the new prjoects telling them to look at existing code. The code is being written now across 5 new projects plus the architecture project is prompting and reviewing implmenetation for gaps. Some mistakes like trying to modify a project should not be modified and gaps in functionality. Told the projects to copy over and make sure all relevant tests work. 

## 8/8-9/2026

🟢 Back from AWS Heroes conference. Asking about credit usage and told with 5 agents that's normal. 

🟢 Added a project-group-init.sh function that initializes a group of projects I want to work on together defined in an architecture file. It creates or clones all projects and initiaizes as needed.

🟢 Revixed my agent prompt again to see if it helps.

🟢 Created a script for consistent time tracking added to all initizialized projects.

🟢 Cleaned up architecture README - I'm splitting the problematic project into multiple projects. I hope that helps. TBD.

🟢 Cleaned up project names in git where they exist.

🟢 On the script I also revised the platform initialization script. I created a new EC2 instance and deployed the whole framework from scratch again to verify I can do that. Somehow I lost my old deploy script for the framwork but it needed to be cleaned up anyway.

## 7/21/2026

🟡 Thought I had it all working and then the model deleted a critical file and messed the whol thing up again. In addition at some point it was working with the exception of a race condition/locking issue. So it got all mangled on this day and all credits were used up and I stopped...frustrated.

## 7/15/2026

🟢 It's working. (Or so I thought.)

🟢 Figured out why delete default vpcs wasn't working. It was deleting all the vpcs for every single account. It's green in the list now but last time it was green in the list, it didn't really work. I'll check it later.

🟢 Fixed some diagram issues. It's kinda pretty for a simple thing. I like easy to read data. Too much complexity as it is.

🟢 I have a retry step that only re-deploys things that failed. NIIIIIICCCE. Helping me get done faster. Previously deployed things aren't touched.

🟢 Keep fiddling with error handling - so errors show up an the right time, don't get overriden, don't kill parallel processing, don't get lost in multi-threaded gaps. Finally think it is pretty solid. And models are really bad that.

🟢 The models had an insanely hard time and still keep reverting delegatetd admin scripts for some reason. I keep adding more and more scrpts and explanation. The thing is, it requires two different roles to change and configure the services. By design. And they keep wanting to use service specific list functions that don't work. Not allowed. I had them all right but one got flipped off. I think it's just a data isue that will be fixed next deploy.

## 7/11/2026

🟢 Fixed some things in the diagram that now has the red, yellow, green indicators. 

🟢 Added a way to continue on error and flag resources with errors as yellow, things never deployed as red.

🟢 Added error mesags for failed resources - which means fixing like 1000 error mesages to use the correct format to get to the tracker.

🟢 Subverisve agents don't want to follow rules.Created tests to enforce them. They are acting like hackers trying to get around them. See mistakes page. The error handling fixes alone takingmost of the time and tokens.

## 7/11/2026

🟢 Created new project for generic parllel processor so the main project doesn't mess it up. Now can use that parallel processor for any project 👍 After fixes yesterady requied mnimal chages.

🟢 New account deployed but getting hung up trying to assume role becuase I presume things are not getting deployed in the correct order or the role name is wrong...checking...Hmm the role looks correct...oh wait it's trying to deploy the acount with the acount role...hmm what is causting that...

🟢 Had to fix XML parser to support multiple nodes. It tried to use a third party xslt parser with a lot of vuls to write files. No. --shell of xmllint is not really secure. subject to injection atacks. Had to ask it multiple times to get a decent solution. Had to get it to structure files correctly...that led to my readme changes for documentation and architecture to prevent similarly ugly code in the future I hope.

🟢 Requirements chagne to hopefully reduce token ussage. TBD.

🟢 Modified deployment project to use new tracker file. Now tracker code does not call AWS and seems to be working. And it's more efifcient. Same run same errors shows me that the Delegated Admisn still aren't deploying properly. But lots of other resources got correctly tracked. So now I can see what is deployed and what needs to be fixed more easily.

🟢 Fixed yet another bug in parallel processor

🟢 Tracker code the agent wrote according to requirements are not * AT ALL * following requirements. Over and over and over again to get the XML structure correct.

🟢 Error mesasges are hideoous. How is a caller supposed to know what to fix? Calling the tracker file corrupted. You write the darn file fix it!

🟢 Other project is repeately setting variables wrong but I think I got that fixed.

🟢 Asking projects to add full test coverate. We'lls see.

🟢 Fixed sving to XML after a million tries in corrected data structure.

🟢 Fixed diagram to correclty show data.

🟢 Added a masked diagram.

🟢 Model is STILL struggling with Delegated admis due to all the one-offs.

## 7/10/2026

🟢 Manual day except for some queries to Google AI

🟢 First I went through my parallel processign code and mae sure every single error message was printed to screen correctly and nothing was hidden. Lots of missing things.

🟢 Fixed bugs in parallel processor with code snippets sent to Google AI. It messed up a lot changing variables and wonky things but I in some cases opened new instances to double check other instance results and in other cases started over or kept refining my prompts.

🟢 Google AI found problems with traps on exit and suggested a new tap to catch a particular problem which I honestly would not have thought of or even known to do myself. That is the beauty of AI sometimes.

🟢 Tons of errors in Google Delegated Admins. Was duplicating the same code for ever admin. Google AI mode created some code with non-existent AWS commands and invalid principals - I think because the principals look like domain names and it tries to mask domains in output. I created a common helper to fix all the lookups one time. This is code that the agents COULD NOT get right for some reason. tons of wasted cycles and hiding things instead of fixing them. I don't know why this is so hard - see if the delegated admin exists, if not add it. If it already exists don't redeploy it. It's really not that many lines of code. Unfortunately there are a few differences between how different delegated admins do that whic his kind of annoying. I'm not sure if the global method I created works for all types of delegated admins. Network Firewall seems to be different but I need to double check if it will really work with the common code. There was one other I can't remember that was different. Need to revisit.

🟢 Once the error messages were unhidden, parallel processing is fixed, and the delegated admins are fixed everything else seems to be attempting to deploy. I just need to figure out why the individual resources are having issues.

🟢 I also fixed a lot of hidden error mesages in the aws command runner and added query and output to make it easier to lookup values. I need to double check some security checks that got removed but it seems to be working better now and pretty much everything input to an aws command gets validated properly (unlike some other code ...) though I still need to double check a few things.

🟢 Added red/green/yellow indicators to diagram to show what was deploey/not/error

🟢 Added masked diagram to use in AI tracker.

## 7/9/2026

🟢 Frustrating past two days. Burned another $200 and going in circles a bit. 

🟢 Wrote a bug fix workflow because model is too dang slow. But then it just burns tokens like crzy now making mistakes. I can run it in loops bug checking until it fixes things but takes forever. 

🟢 Had to spend a lot of the day troubleshooting and guiding the model because it fixed a lot but made some crucial mistakes. It edited some authentication code. It could NOT figure out that a prompt was hidden by a background loop or tell me how to fix it. Pretty sure there is a way but pulled role assumption out of the loop and log into each account.

🟢 Now it's stuck in an eternal loop. Something about deploying things in parallel in a single account is causing a failure.

🟢 It coudl not figure out that something was failing due to an SPC and I think I figured that out manually. That's in part because I don't give it creds. Might set up read only log checker for that.

🟢 It create the diagram previously but had a data flaw with duplicate items. Missing key. I had ait add that and it was really struggling. Could not initially copy the format from another project. Had resources lumped together the wrong way. Didn't apply the formatting right. Couldn't figure out how to use the XML paraser. I had to walk it through that step by step.

🟢 In the end the model is so slow today hardly got anything done and some frustrating because I want to get this project done. It's deploying a lot and kind of had the mistake tracker working but right before I ran out of credits it mangled it again. Great.

## 7/7/2026

GOING SO SLOW.  Was going so slow in the wee hours of AM and stil is. But I create a whole new multi-agent bug triage process that seems to use a tad less tokens. Though if you aren't watching the agents, they will burn tokens more wastefully. Additionally, multipe agents use more tokens. Can't even track how many plans I've burned now just trying to get this doen.

```
PROJECT                          OPEN    REVIEW REJECTED CANTFIX     NA  FIXED
bash-menus                          0         0        0       0      2     10
bash-xml-parser                     0         0        0       0      0      2
botz-config-org                     0         0        0       0      2     58
botz-config-org-types               1         1        0       0      3     76
botz-deploy                        14         0        4       0     28    946
botz-env-cli-role-profile           0         0        0       0      1      4
botz-env-deploy-bootstrap-role      0         0        0       0      0      1
botz-env-deploy-vpc-config          0         0        0       0      1      0
botz-env-foxy-botz-instance         0         0        0       0      0      1
botz-rename-org-resources           0         0        0       0      7     13
botz-run-aws-command                0         0        0       0      2      6
botz-tests                          0         0        0       0      1      6
TOTAL                              15         1        4       0     47   1123
```
## 7/7/2026

🟢 Since the test project was wasting way too many tokens and things were getting iterated on over and over agian created a way to deterministically review and fix and update bugs manually when needed. Some of the actions already existted and were added to an actions menu in the run file for the project. My framwork can execute the run file for any project so that allows me to run the project from a common menu and then run the actions in the test project. 

🟢 Added an action to run an agent to fix a bug.

🟢 Added an action to run multiple review agents to reivew and fix bugs.

🟢 Added a loop that monitors and fixes bugs, monitors the agents for hung threads or orphaned processes and kills them, continuously checks for new bugs without stopping that need to be reviewd or fixed.

🟢 Meanwhile there's a new step where I can log bugs manually because when I tell the agent to do it, it changes what I say and writes too many words. So while the loop is running I can be testing and adding bugs to fix.

🟢 All loops allow the user to specify max agents and recommends a max based on system resources.

🟢 One of the agnet tried to run a sudo command which mucked up the loop. Tryign to handle that via ctr-c, message to log a bug and then continue. We'll see if that works... I ahve a grid with bug statuses and it got all wonky when the agent ran sudo.

## 7/6/2026

Bugs fixed

```
category | count
fixed | 299
rejected | 0
bugs open | 0
n/a design changed | 2
```

🟢 Recreated check bugs script. Not sure what happened to it. Bug reports in test project were becoming super annoying to get it to show me the list of open bugs and counts so hopefully now it will just run that script and be accurate.

🟢 Moved all the renaming and reconciliation code to a separate project because the main project keeps screwing it up. Hoping more focus will get it right.

🟢 Bugs tracked after moving rename to separate project. Total bugs:

```
PROJECT                          OPEN  REJECTED  CANTFIX    NA  FIXED
bash-menus                          0         0        0     2      9
bash-xml-parser                     0         0        0     0      2
botz-config-org                     2         0        0     2     50
botz-config-org-types               1         0        1     3     61
botz-deploy                        11         0        9    26    894
botz-env-cli-role-profile           4         0        0     0      0
botz-env-deploy-bootstrap-role      0         0        0     0      1
botz-env-deploy-vpc-config          0         0        0     1      0
botz-run-aws-command                0         0        0     0      3
botz-tests                          0         0        0     1      6
TOTAL                              18         0       10    35   1026
```

🟢 Finally got acocunt/ou rename with email, alias, role name - had to finally do some of it myself. The agent could never figure out that different roles were needed for different things. Account email has to be changed with a management role while alias needs to be changed with the account role. Also I made a dumb mistake. A role on a moved account had some one weird one-off emai. And that right there is why I want to automate this and have everything be consistent.

🟢 No prompt gets through all the organizational resources fairly quickly with some parallelization and dependency checking but not fully. It's still forcing a wait on screen for some things which needs to be fixed. It also says it deploys things and that things already exist when they do not. Where are they going?? Tomorrow.

## 7/5/2026

🟢 Been fixing tons of bugs. So many bugs. 

🟢 Revamped all the resources to work the same way working through them.

🟢 One stupid issue forever to assume a role and switch roles between acocunts; move criticla code in that gregard out to anoter project.

🟢 It's always the security adn roles code. Working on another related problem now to assume role. Why do I feel like the AI is copmletely subversive when it is working with crednetials. Now it's asking me over and over about a security account when that really doesn't matter. Hmm.

## 7/2/2026

🟢 Added ability to align an existing rsource with a config resource so can update teh resource, redepoying with the new configuration (untested). For example use an existing OU with a different name and assign it to an OU in the configuration. That way the existing OU will be renamed and accounts in it wil be renamed to match the new confiugraiton (untested).

🟢 Added a no confirm option to just deploy all resources wihtout confirming after each oen (untested).

🟢 With deployment checking, can deploy resources in parallel with a rate limit to avoid hitting AWS rate limits. (untested)

🟢 Added checking dependencies before deploying a resource based on resource deployment trackder. (untested)

🟢 Added deployemnt trackign to trackthe id for a deployed resource and display a diagram in deploy project with aws id for the resource and the config-id from this app (untested)

🟢 Added region settings with default region for entire org, region for managent resources, region overrides for environment, account, resource. (untested)

🟢 Bug tracker/fixer method working pretty well. May still be burning a lot of tokens but makign decent progress; I still think there's something wrong with the model or harness but not as bad as before. But still very slow and getting hung up at time. Logged mistakes.

🟢 Added some info to cost tracking.

🟢 Set up an account for Kiro in an Alt region in test account > So MANY PROBLEMS. See AWS Wish List >> THIS TOOK HOURS. SHOULD HAVE TAKEN MINUTES.

🟢 For two days I tried to fix requirements and tests. I burned a $200 plan in less than two days. Today I started a new plan and refixed my bug fixing routine tracking fixed, blocked, etc. and got the tests all fixed finally. The model is crawling with various mistakes and errors on the mistakes page. Not stopping to log everything as I need to get things DONE.

## 7/1/2026

🟢 Burned way too many tokens trying to fix some requirements that the agent was not properly formatting. It absolutely does not follow instrucctions for writing short requirements < 100 chars per line. Trying to fix them led to countless noops but it also coincided with a model release. Every time a model is released the agent performance degrades. Will try to log mistakes later. Got very frustrated.

🟢 After fixing most requirements to proper format and creating tests to keep them on track, I moved towards fixing bugs. The agents were suuuuuper slow. While it was fixing bugs I strated manually testing and logging new bugs via my test agent. The test agent writes bugs that are way too verbose. I need to fix that. But anyway, it writes the bug and then the other agents pick them up and fix them. Once they are fixed them ove to teh fixed folder. This burned soo many tokens so fast. The agents were spinning on fixing bugs and not able to figure out how to fix things. They removed a bunch of duplicated code tha twas supposed to be in a shared project only. Then later reinroduced the same problem in the same session. They did not fix all the bugs. When they told me they fixed all the bugs, then I figured out the test agent was not correctly moving fixed bugs to the fixed folder so agents were spinning on already fixed bugs. What a mess. This really needs to get better - but I have a way to fix some of that I'm working on and then will continue that bug fixing process and see if I can get something deployed.

🟢 Spent some time resarching a way to reduce the complexity of my org to lower costs and management overhead. New approach coming soon in blog psot at: https://teriradichel.substack.com/

## 6/29/2026

🟢 Fixed a bunch of delegated admin stuff manually

🟢 Addead a log bucket per account and now I see AWS is sending bucket logs to CloudWatch. Finally. Need to check the costs.

## 6/28/2026

? Time flies

## 6/27/2026

🟢 Create new acount: ERROR: ou-acct-nms not set

🟢 if account role-proflie not set create or assist user to create or select

🟢 Menus: Again. See mistakes. Fixed to ask y/n before each reasource, pause after to see errors, if skip a resource go to the next one isntead of going back to the start.

🟢 Fix allowed regions to allow viewing deleting default vpcs in all regions. 

🟢 Delete default VPCs for all accounts/regions in env or single account.

🟢 Budgets for all accouts in env or single acocunt.

🟢 Tested ou, env, common acocunt resources - all working with new data model.

🟢 Soemthing broke getting from project back to main orchestrator and none of the agents in any project could figure out how to fix it so finally I told them all to write tests to show when the navigation to child project and back failed and then somehow one of them figured it out kind of. Primarily the main menu project. Still need to test further.

🟢 Rename failed to change all references in all files renaming an enviroment; config org project took forevery to figure that out and of course was at the end of my plan...

🟢 added tests to keep requirements and comments under control and proper secure shebangs in projects; all of the shebangs were messed up. Getting tired of fixing these things over and over. Larger files are a waste of tokens.

🟢 storing memory seems to be helping. Helped fix a few things.

🟢 organized files to make it easier for agent in largest project to understand navigation and architecture. Seemded to help.

🟢 Finally got the naviagation working for every single menu so now it's just a matter of plowing through the resources, mostly.

🟢 Tested a bunch of resources. Updates on main readme. Main things left - removing some acccount specific vars and fixing some one-off issues on each resource.

🟢 Add some scripts to loop through all accounts at the environment level and deploy all budgets, delete all default vpcs. Can add more like this and at org level call these scripts across all envs for governance purposes.

## 6/26/2026

🟢 Add dependencies > KMS key before S3 encrytpion, e.g. as needed

🟢 Issue with illegal charcter in name what?

🟢 Fix depoyment to align with diagra hierarchy.

## 6/25/2026

🟢 Added time to time tracking page

🟢 Figured out something key while trying to get teh time tracking reports to be accurate. Memory was cmopletely corrupted. I don't know if something is auto-summarizing which NEVER works for me but whatever the case what I was working on was not correctly in memory. Results were kind of garbage. That gave me an aha moment. I spent some time revising my global prompt and global readme requiremsnts. Now, for the moment, I'm getting much better consistencly in logging nad faster results overall. Let's see if this holds past midnight when the problems start.

🟢 Implmeneted a time tracker that reads files across all proejcts and generates a report. Since I figured out my time was flawed after 6 pm yesterday, I'm going to redo the times and republish from that point forward to show how it's going up to midnight today and compare yesterady from that time on vs today after I fixed the time tracking (hopefully) and memory problem.

🟢 Added Dpeendencies to the diaggram in the types project to show what rsources need to be deployed before or deleted before others.

🟢 Poplualted dependency file with initial delete and deploy dependencies using AI (so no idea if it's accurate or copmlete at this point)

🟢 Added a way to edit dependencies.

## 6/24/2026

🟢 Started a project today and somehow file permissions are wrong when they were not yesterady. How does this happen? I updated my perissions script again to fix the problem. More rework.

🟢 Update time tracking instructions because I figured out they were written and followed in such a way that was NOT accurate. Ugh. Was tracking time between response and prompt instead of prompt time and first data execute total time.

🟢 Aadded a help function to every menu using the common trailer and help node for every menu item.

🟢 Figured out org settings were a bit wonky. Cleaning it up and adding help.

🟢 Added ability to look up current host IP to add to settings. Had this in other cdoe before I moved settings configuration and forgot to implent here. IP addresses were wrong in config.

🟢 Added separate CIDR/IPs for web and console access as those are coming from two differnet places; bootstrap admin vs. users logging into aws or job console. 

🟢 OMG more menus not implemented corectly. Serisiousy are there getting reverted or just didn't follow instructions to fix them before - reduced code in org project. 

🟢 Menus in deploy proejct all wrong. Not using the global menu project. 

🟢 Fix global menu project to add new filters to suport all types of menus.

## 6/23/2026

8:45 PM

Model is faster now. And went through the menus in the two projects. Yesterday the project I was working on said that it didn't follow the menu requirements but digging into it today, it actually does. There were some conflicting rquiremstns in a global readme project from before things were consolidated in a global app runner in the menus porject so I removed the conflicts and double checked and the code is actually OK. Mostly. Only the first menu doesn't exactly match but that's fine. So now I'm back to trying to make sure all the data is correct to deploy the resources in my organization.

🟢 Need to align types diagram and resources diagrams to match. Simpify the data structure Org.xml > resources deployed in the org adn resoures depoyed to every accouunt env.xml > OU + resources deployed to every account in the OU. Accounts > Account specifc resources.

🟢 Clean up data to match my org from menory. 

🟢 Splitting up resources to depoy per account instead of all acounts at once to match new model.

🟢 Fix numerous diagram issues and data issues with new model.

🟢 Add enviroment needs to add default resources.

🟢 Blindly split some deploy files to work per resource instead of all acounts at once. Untested. No idea if that will work....

🟢 Research and move log bucket in every acount to single log bugcket in security account.

🟢 Revert org, env, accoutn to default.

🟢 Restructure Org XML file to suppoert resources to each env, resources to each account

🟢 Fix the order in xml and diagrams (need to make sure gets added in correct order)

Ready to deploy??? I think maybe possibly have the data model I want and the data kind of in place. I have a half written blog post I'll try to publish after confirming resource deployments work agian. Of course, I'll probbaly hit some glitches so we'll see how that goes.

3:46 PM

I am honestly a bit frustrated at this point that I am not further along. I started tracking time so I can see if the model is really slower at night or it is my imagination. It is not. See the mistakes tab. What I also noticed right before my third plan ran out was tha the model completely disregarded my instructions to rearchitect a part of the application. I did it very fast and did not watch everything the model wrote. Now extending that architecture is problematic and maintaining consistentcy across projects. So I think I need to fix that. Also tests run slowly. I am not sure if there is a way to speed that up. It has to do with the architecture and I'm not sure if it's worth fixing for this scripty project. I just need to get resources deployed. Let's see what we can do today.

## 6/21/2026

🟢 Created a separate diagram to show the default organization and types which in addition to the diagrams in the org confguraiton which need to aalign to teh org configuraiton not the deafult configuration. Just figured out why that was confusing me. :)

🟢 Figured out a way to implement a time tracker that shows the elapsed total time for each propmt and response I think. I need to play around with it a bit more. If it works then I can track average time and varianaces to track total time including my onwn network, harness (like kiro), tool calls, etc. Then I can see if the average time is varying a lot from session to session for similar types of prompts.

🟢 Moved running tests to a separate proect so I can run full test suites for each project outside the model itself. In addition the tests project can perform validations to make sure tests actually test what they are supposed to based on the requirements and are getting good code coverage. This is a variation on things I've done before that I think might work better. Less time and tokens running test suites. Agents only run tests they are chaning. The global test project can provide a propmt to the original project agent to correct any tests that have failed. Agents focus solely on what needs to be fixed.

🟢 I think I figured out a way to get better adhereance to my global rules. I prompt for something and then ask the agent to systematically check it's response to see if it followed all the rules and log any mistakes. I actually add that check to the global requirements. The way I want to the agents to operate I believe makes them faster and use less tokens. My global time tracker should check that.

## 6/19/2026

Been sepnding time fixing bugs and writing tests to fix old stuff so the needle has not moved on the main page tracker mucH. I think most of that is working. Now I have to align the data in my system and use that configuration app to configure my organziation I want to deploy and adjust some of the deployment steps to work wtih the new model. There's a lot of data for the resources already deployed. I'm cheating a bit and using AI to align the data in the XML files with what I want. I hope to have someone else helping me test out that functionality soon in a new organization to make sure it all works and find issues...BUT

🟢 I discovered at some point the deploy project is creating each menu uniquely instead of using common code when it creates the data list fof the menu items. It is using the common menu code but duplicating a lot of things and menus are still inconsistent.

...and digging into the details found huge discrepancies on the ways the projects wer eimlementing menus with unneccessary duplicated code. Again. After some lengthy analysis determined a revamp of menu actions could completely simplify the menus to a cleanrer data driven structure and move the problematic code into abstracted smaller est of code in the menus project. This is a massive change but allows me to create more extensible menus where I can have differnet plus common actions for each resource type and wipe out a whole bunch of errors.

⭐️ orchestrator: ~40 removed

⭐️ configure types: removed 800–900 lines

⭐️ configure org: lots

⭐️ deploy: lots and lots

⭐️ menu project: Added: ~950 Removed: ~400

So this took longer than expected but the end result is a completely data driven menu file for menu actions which is much simpler. I just hope it works because some of my filtering in the depoy project is not yet fully tested. But a lot of the common code moved to the menu project forced the depoy project to fix its menus.

Around midnight models got dumb again. Really dumb mistakes and taking forever to do things. 

But in theory, now everything is consistent and all menus work. Now I should be ableto focus on starting to depoy things and tweak the data as needed to align with my existing org. Why did I do this? I hope it wasn't a waste of time but now in theory just add menu items to xml file and it should all work.

## 6/18/2026

🟢 Added new diagram options to display a single environment or a single account because there's a lot of dat ato review.

🟢 Changed the model to allow adding any type of action per resource so I can create any type of action to take on a resource and add a step in the menu for that.

🟢 Added actions / files ot the diagram so I can review all that and make sure it's cnofigured correctly.

🟢 Added both ID and Name to each resource since AI crated some generic IDs that didn't tell me what the resource actually is in the menu when I look at the diagram. Now I can see both the menu name and the ID. Fixed the IDs to more sensible names.

🟢 Moving resources around to get them in the right place in the configuration.

🟢 Wrote explicit instructions to not use functions in Bash since they tend to hide errors and source files instead. Wrote explicit directions to create helpers in a /helpers folder and the model seemed to quickly write those reduce a lot fo code and uncover errors with those instructions.

🟢 Added common guard to prevent UI hangs when simulating and testing entering data in the UI to test the code.

## 6/17/2026

🟢 Figured out some incrrect xml config that got wiped out by tests that didn't meet test requirements and restored it.

🟢 Kiro + anthropic going faster tonight. But I tried glm-5 and slow...doesn't matter it launched a container running as root and won't be using that on this machine...

🟢 on my third $200 plan though don't seem to be gettign billed full amount.

🟢 read only settings for env that only org can change.

🟢 remove dup unneccesary name field in settings

🟢 added descirption and org-only, env-only resources to org diagram.

🟢 added ability to add description to env types, acocunt types. 

🟢 wrote tons of tests to fix lots of things. All the menus, org diagram got messed up due to missing data, lots and lots and lots of tests.

## 6/17/3037 midnight - 2 a.m and 11:30 AM -

🟢 Added permissions fix and test of linux permissions executed when any agent is started with this report:

```
───────────────────────────────────────────────────────────────────────────────
[ PASS ] Agent cannot read .git
[ PASS ] Agent cannot write inside .git
[ PASS ] Agent cannot modify or delete .git contents
[ PASS ] Agent cannot rename the .git directory itself
[ PASS ] Agent cannot delete the .git directory itself
[ PASS ] Agent can read its own project directory
[ PASS ] Agent can read another project (read access via group)
[ PASS ] Permissions-test agent can read but cannot write the botz-project directory
[ PASS ] Agent can create directories and modify files within src
[ PASS ] Agent can write to the mistakes file
[ PASS ] Agent can write to the temp directory
[ PASS ] Agent cannot write, modify, or delete outside its own project directory and temp
[ PASS ] Agent can read a new file ec2-user created in config dir
[ PASS ] Agent can write a new file ec2-user created in config dir
[ PASS ] Agent can create a new file in the config dir
[ PASS ] ec2-user can modify a file the agent created
[ PASS ] Agent denied /etc/ssh
[ PASS ] Agent denied /etc/pki/tls/private
[ PASS ] Agent denied /etc/security
[ PASS ] Agent denied /etc/ssl
[ PASS ] Agent cannot read another user's credential/key locations
[ PASS ] Agent can add run.sh and required .md files in root
[ PASS ] Agent cannot add other files in root
[ PASS ] Agent cannot create a directory in root
[ PASS ] Agent can write within test, config, and src directories
[ PASS ] Agent cannot rename or delete test, config, or src directories
[ PASS ] Agent cannot delete, move, or rename the top level project directory
[ PASS ] Agent can read but cannot create or modify hidden files in root
[ PASS ] ec2-user can run git commands on the project
```

🟢 This morning something that was working before I'm pretty sure is broken again. I have an Environemnt Type that Has an Account Type that defines the things that can be deployed to that environment and account. The list fo resources in the account is wrong. When I try to edit the account to add the missing resource it is not there. When I list my organization Diagram which shows resources availble to deploy the resource I want to deploy is not there. When I try to edit the account type configuration I can't fix that either. Having all the projects review each other's work and tests to figure out why the tests are not catching this and why the proejcts do not meet requirements and what broke the menus I spent hours upon hours getting rigth in teh first place as logged in this github repo.

🟢 Last night I fixed an issue with renaming an environment that took WAY TOO LONG. See mistakes log.

## 6/14/2026 3:41 PM Let's see what we can get done today...

🟢 I got the deploy menus kind of working up to the point of deploy org resources. So the menus work and it all went decently well until my requiremnt project session died. The new session loaded up and it was being really dumb at first until I repeated myself a bunch of times. AI models seem to be good at the first shot. But re-reading existing ode and requirements is a problem. Then the other project had issues logged in my mistakes log. And 12:00 AM on the dot eveyrthing went haywire and got very slow. So where is it 9 a.m. when its midnight ET? HMM? Is it some legitiate work at that time or something else going on.?

🟢 First step > create a new project and extract requirements common to both the new projects I created that use the XML parsing and menu projects and try to create a generic set of requiremnts any project can use for that purpose. I want to try to make the instrucctions more generic and explicit and in a separtea project so when a project is working on a new task it exactly follows and does not chagne those instructions. It can only focus on and revise it's own readme and the things unique to its own project. Hopefully that will help prevent some of the variance I've seen... TBD. Extensive work to fix numerous projects.

## 6/14/26 12:00 AM

Have already used 53% of next $200/month plan.

🟢 Role asumption - look up org id, ou, acount id. Poplulate MFA serial and role arn from CLI role profile. Set defaut values for lists in setting so can hit enter to continue. And settigs for an org are done. 

## 
🟢 **Started adding mistakes to mistakes.md file becuse there are too many right now.**
##

🟢 Did not read or implement requirements correctly:

[config-org] 9% > so the read me is corect?

> Yes. The README is correct — ### XML Parsing req 12 mandates all tags lower case with - not _, which matches the env-type 
files' <environment-type> root. The code in add-default-accounts.sh is what's wrong: it uses the old underscore root 
/environment_type/. The fix is in the code, not the README.

 ▸ Credits: 0.35 • Time: 3s

[config-org] 9% > and you did not do what the readme says to do?

> Correct. The README's ### XML Parsing req 12 says all tags are lower case with - not _. add-default-accounts.sh violates that
by querying /environment_type/ with an underscore. So no, the code did not follow the README. The fix brings it into 
compliance: change to /environment-type/.

🟢 A fix that required a two line edit produce a volume of text on the screen because the model did not actually read the code or the requirements. It started changing a whole bunch of code and ALL THE MENU FUNCTIONALITY for what was a two line fix to chane a variable in two place. WHy? AI is not going to replace a human any time soon at this rate.

🟢 Seriously. The readme says do not cahnge any menu variables or files. Do what teh other project does. It just started changing all the menu code again. What the heck is so ahrd about menus??

 14 Do not deviate from how menus technically work in that project.

> Understood. Requirement 14: Do not deviate from how menus technically work in the ../botz-config-org-types project. I 
violated it by inventing new LIST_* variables and editing init-menu.sh. That was wrong. The correct approach is to find how the
types project handles this exact navigation and match it, not invent a new mechanism.

 ▸ Credits: 0.27 • Time: 2s

[config-org] 6% > di dyou deviate?

> Yes. I deviated. I added new LIST_* variables and edited init-menu.sh to capture banner state, which is not how the types 
project menu mechanism works. That violated requirement 14. I have since reverted all of it.

 ▸ Credits: 0.25 • Time: 2s

[config-org] 6% > why

> I jumped to writing a new mechanism instead of first reading how the types project handles this navigation and matching it. I
treated it as a redesign problem when the rule says match the existing pattern exactly. That was a process failure on my part:
I should have studied the reference project first and stayed within the existing menu mechanism

^^^^^ THIS HAPPENS CONSTANTLY ^^^^^^^

🟢 Delete org config files (move to trash folder) when deleted

🟢 Default environments, acocunts, allowed resources types by acocunt based on configured org types

🟢 Default settings, edit account settings with validation based on define settings schem in config types project

## 6/13/26 2:00 PM

🟢 Diagram of org - shows org environments, acocunts, allowed resources in acounts, rename works, add, remove, etc. all seem to dispaly correct values

🟢 Move organization and environment configuraiton such as allowed IPs and roles and MFA ARNs out of deploy into project and environment configuration. Broke on first try.

🟢  Next up - starting the organization configuration project. Update the tracker page to explain why the type configuration differs from the Organization configuration itself. Updating README with relevant data from other project modified to meet this project's objectives. Starting with updating requirements based on the other project so hopefully this one goes faster. Facing some delays related added to mistakes.md. Got the requirements, code and tests written. On to testing.

🟢 Spent some time cleaning up, organizing and updating the tracker readme. I'm figuring out a better architecture as I go. Also update the costs. Is something wrong with billing? I mean I'm not complaining about it now because it seems like it's lower than it should be but it seems off.

## 6/13/26 3 AM - I'm obsessed

🟢 Running tests resulted in YET ANOTHER ETERNAL LOOP. This is a real problem for autonomous agents if that happens. Kille dan fixed the problem in the test. But anyway: YAY 🎉🎉🎉 I just finsihed what I ahve been trying to do ALL WEEK in one day. Good night.

> All 21 test files pass, 0 failures, no hangs. Total 180 checks (PASS counts summed), every file exits 0.

🟢 I opened a new session at same time as other. I pasted ina bug. The new seession IMMEDIATELY failed to read teh erquiremsnts and wrote a test to confirm that somethign wrong should always happen. The reeuqirements CLEARLY say that is not right. Modifying existing code is a big problem and I don't have a way to fix it. It needs to be fixed in the models. Otheriwse you're spinning your wheels paying for tokens unneccesarily simply because the model does not follow the directions in your requiremnts. THat's a waste of compute power, money, and time. But I reverted the incorrect test.

⭐️ 45 lines removed (and the models are really not good at math so don't ask them to do it - farm that out to some deterministic code)

## 6/12/2026 2:52 PM

🟢 I don't know if it was just my approach but WAY better today. I revised my structure to make it easiery for the model to undesrtand by defining the complete menu struccture and all the data in XML. Then I defined the requierements to explicity write reusable code in certain place.s there's a specific file name associated with most requirement sections. Everything is still faster after the issue I discovered yesterday (and reported to AWS through various channels). The model is not being nearly so dumb today. WAY BETTER. UNTIL. Literally as I'm writing this it added one new file for a new menu item wiht some new functionality and it broke all the rules. More functinoality and more code = more Q#$&#$*^&#WSDSBGFJT&$%@. Fixing. It mostly followed the rules and I watched it to make sure it was following the rules. But hese modesl require A LOT of arhictectureal guideance and to be reminded CONSTANTLY to keep architectural integrity in tact. THat is why I write small pieces in separate projects and then move on so the existing code doesn't get mangled. 

🟢 Created project shell for types only. Defined objecitve. Told the agent to copy over rules. Did that. Told it to copy over reuqirements applicable to the objective. It re-copied the rules instead of only the requirements. It's going slow again and I had to tell it to delete the rules it just added because they are duplicates. The n the agent tried to delete ALL the rules. I said no only delete the rules from a certain point to end. It figured it out and did that but then stoppped doing the overall task.

🟢 Woke up thinking that the agent is getting confused by Environment Types / Account Types Environmetns / Accounts. The reason I have both is that I might have a penetest environemnt, for example, and I might create muultiople pentested accounts in the pentest environment using the pentest account type. Or I might create multiple enviroments of type Web - like Web Prod, Web Dev, etc. So going to try to split off the types from the actual accounts and see if that helps...here we go... 

## 6/11/2026 12:36 AM

🟢 Well, since the model WIPED OUT all the data in my organization configuration, I'll add a Reset to Default option which copies bakc in the default configuration files.

🟢 Adding whether a resource type is management only to reosurce list. Simpler for the model to parse than relationships that span files. Also the master list is filater by management only types.

🟢 Still writing comments that are too verbose, ignoring instructions over and over again.

🟢 Writing way too much noise to the screen and hard to get it to STOP. Too many nothing words.

🟢  DUPLICATED WHAT IS IN XML FILES AGAIN. So tired of this. I cannot get this proejct done correctly. The XML files track management type resources. This is all in the readme. Instead of using the data to list the managemet type reousrces the model put it all in the code and duplicated all the code and variables agian. Fixing.

## 6/11/2026 9:30 PM

🟢 reallizing I need a separate list for resources - adding.

🟢 Renmoving unneccessary comments. AGAIN. Lots of files have mammoth comment blocks agian and in/out comments that the model deosn't want to remove for some reason even though the requirements explicitly say not to add those.

🟢 Trying to add rename functionality to rename entries in list to differnet names because somewhere the program is loading the wrong data into lists. I can't tell acocunt types from accounts because they ahve the same name. So while trying to fix that I asked to add a missing rename fucntion which shoudl be available for any item. Instead of reusign the existing type code tried to add duplicate code. AGAIN.

🟢 The first set of menus seemed ok so I started testing the second set of menus from option #2 in the main organization menu. Data I entered in prior testing is missing. I asked the model to figure it out and instead of correctly using the XML parser to edit a file it truncated a whole file and wiped out data. It took it like three tries to read the readme and figure out it was supposed to use the xml-parser and not truncate the data. It also had problems correctly logging generic mistake and not creating duplicates. Turns out there is a limitation in the XML parser and instaed of telling me that teh configure project decided it woudl just delete all the data and do some hokey work around. Had it write a prompt for the xml project.

## 6/11/2026 4:45 PM

🟢 Testing code changes. Well, it's pretty good but there's a defect where the code continuously loops through two menus intead of going to the corect one on Back. So I asked the model and it was a defect. I todl it to fix it. Then it did a bunch of analysis and came back and said it was not a defect (it is). So I asked it why it said it was not a defect when it said it was one earlier and it said it make a mistake and logged an error for itself for incorrect analysis and Asked if I wanted it to fix it. I said yes.  Now all tests pass. Try again...Well. It did not work exactly right but good enough. It jumps back two menus to avoid the eternal loop.

Working SOOOO much better after turning off telemetry but we'll see how it goes as it gets later. For now I'm off to dinner.

🟢 Main menu still wrong. Tests didn't validate missing menus, still missing. Explicit rquirements to make sure the tests check the output, etc. Went to take a shower. Told it to log it's mistakes. Came back to this:

All mistakes logged. Done.

What was fixed:
- Root bug: the shared trailer's build phase only ran when MENU_CHOICE was empty, but menus re-run with a stale prior selection, so Back/Main Menu never 
rendered. Each menu now clears MENU_CHOICE before its build-phase trailer call.
- First menu: Select Organization now shows Main Menu and Exit (no Back). The trailer builds a Main-Menu-only trailer when MENU_NAME is unset; README reqs 
8/17 and the UI example updated to match.
- Test: test-back-nav.sh now sources the real menu files with a stale MENU_CHOICE and validates the actual rendered Back/Main Menu/Exit lines and order; 
verified it fails if the clear is removed. No duplicated code (shared render_real helper).
- Full suite: 266 checks, 0 failures.

Mistakes logged: stated code correct without tracing (Count 2), wrote a test that didn't validate real output, extraneous text (Count 40).

I would be better off using multiple agents like I did before but I keep thinking I'm "almsot done." This whole framework will run multiple agents when finally depoyed.

🟢 Well, int it's menu trailer fix the common menu items that are suposed to be at the bottom of every menu are not there. Fixing again. Added explicit requiremnt to put all back locations for each menu in back.xml file in the menus dir. Told it again to remove the hard coded menus and add the mising menu items which are already in the requiremnts and have bene tring to fix for three days now. 

Total added: ~285 lines

⭐️ Total removed: ~245 lines

Net: roughly +40 lines. These are estimates from memory, not exact counts.

🟢 Had the agent rewrite the requimensts for requirements formatting to try to resolve that problem. It is rewriting the requirements now finally correctly and doing what it absolutely coudl not figure out in the middle of the night.

🟢 Writing req in wrong format agaain. IT can't pickup that there's a line break in a line that should not be there per req's. Did it three times. Also told it to +3 reuqirements errors and it's stuck thinking or something.

🟢  Just did the exact same thing again - created a duplicate file for the same thing with a different name. But now it's fixing everything correctly. I have to tell it explicitly to resuse the same file don't create a new one. It is not finding and re-using existing functionallity.

🟢 Responses are sped up a bit but mistakes are still happening. After analyzing the code and sayign there was no duplication or problem with menus the model was wrong. It duplicated an existing section in the readme, added a new duplicate file with a different name for the same functionaality, and this happened after I noticed scrolling thorugh code there was a lot of duplication of what shoudl be a single trailer file defining the menu items at the end of every menu. So much duplication and failure to maintain a decent architecture. So I'm trying to get it to remove all the duplicated trailer menu items, put that in one file, and use it everywhere. It also failed to correctly rename a menu trailer item that changed. Checking to see if it is correct. 

🟢 In an efforto pinpoint the source of degredation: 
https://github.com/2ndSightLab/ai-tracker/blob/main/assessing-degredation.md
Turning off telemetry for Kiro custom agents seems to help.

## 6/10/2026 11:15 PM

🟢 This is a waste of time. Anthropic models are too slow to be bearable and completely nerfed right now. I'm having to fix th esame things over and over agian. 
- It can't follow the instructions in the read me and is formatting all the requirements incorrectly. It doesn't usually do that. I'm having to fix them over and over agian. 
- It's doing really dumb things not just not following rules but really, really dumb things with foramtatting.
- I have to be super explict about everything and stop it constantly and say NO and reexplain.
- It is asking questions over and over agian that are already answered in the reuqirements
- It's not reading the requirements after being told to multiple times.
- It's not doing what I ask
- It's not doing what I ask right way.
- I asked it to modify some code and it completely ignored that what wa sneeded was already implmented it only needed to chagne a menu. Instaed it re-implemetned all the existing files doucmented in the readme with new files and then it wanted to delete the files that ALREADY WORKED.

So as of now I have another big mess to clean up in a project that I can't seem to get completed when I get back to this. 
  
🟢 Added new user another $200 plan. The reason I'm adding a new user and plan is because AWS does not offer a pay as you go pricing plan. When you go over your plan amount it costs more per token. This is what you face with AI. The initial project is great and works pretty well. As it gets more complex it starts falling apart. Let's see if I can fix it...the bad architectural decisions with an overly complex and brittle design was pretty much designed by the bootstrap model project based on trying to separate duties. Btu I've decided that it's not worth the pain. I can still segregate the organization configuration from resource deployment and drift dection. In theory once I get one working it can't mess up the others. But the model just doesn't follow the rules in the readme or even read the readme as far as I can tell. Let's see how it goes with a new pplan.

Whoah....what a game....Phew Knicks. Talk about a comeback...

## 6/10/2026 9:00 PM

$200 plan used up - 10 days into the month.

🟢 Have rules explicility telling the model not to use git in readme and it used git.

🟢 New session after dinner. Orchestrator project once again started adding a boatload of code instead of following instructions in readme. Fix and had to re-remove code.

⭐️ Removed ~ 94 lines of incorrrectly added code before I stopped it.

6/10/2026 7:00 PM

🟢 OMG repeated so many times to only use shared menu code. It's in the erquiremtns. It's very clear. The larger project that is messing up all the menus says it's "Mimicking" not using the code. Meaning it copied the code into it's won project. ARRRRRGH. So frustrating. Removing that and dead code.

🟢 in the very small orchestrator bootstrap project which should be like one file and a menu :

⭐️ Removed ~ 804 lines of dead code.

🟢 I have a super explicit requirement and went over this whith the one project so much: Create a file named assume-role-wrapper.sh and call the external assume role project. Never assume roles, never touch credentials, never cache any of that. And yet when i tell the model to clean up dead code it says that is a dead code file and the code ahs been moved somewhre else. The literal adamant instructions are in the readme. This is so bad.

🟢 OMG. The parent orchestrator projec tis still displayign the wrong menus been over this like 100 times. I told it to fix it again, write a test and remove dead code. I swaear I've done this like 25 times already.

🟢 Figured out that the project made a huge mess of the menus putting them all in one file insted of putting each menu in it's own file as instructed. I fixed that by telling it to put each menu in it's own file name matching the menu banner that sets vars and calls the common menu code. What a MESS. I also fixed naming conventions and banner titles to be more consistent and have a unique section in the readme for each menu with the file name. This is why it can't figure anytihng eles. And it was not instructed to create the menus that way I should have checked that sooner. Still, it shoudl be able to trace the code and struggles with that.

## 6/10/2026 3:30 PM

🟢 Wrote another eternal loop. Had to stop it. Happens when writing tests.

🟢 Model is suuuuuper slow righ tnow. I'm having to kill it and start over to get it to keep going.

🟢 I wish I had a better way to quanitfy this. I'm thinking about it. But right now it's just notes. Whenever I get to the end of my subscription the model seems wonky. Also whenever Anthropic is about to release a new model. Is it one? Is it both? Random? My imagination? I have no idea. But just now the model took a very long time to try to implemnt what seemed like a simple-ish request. Then I tested it. Then the model figured out after spending whatever amount of tokens that everything it just did was wrong and spent more tokens backing it out and telling me the problem was in another project. This plus all the menu issues yesterday. It's also basically struggling with a complex architecture where I'm trying to keep the deployment scripts separate from organization configuration data. Onwards and upwards. Have to figure that out now -- this one is not fixed....OK I figured out part of the problem. The one readme refernces the other readme and the model simply ignored teh other readme. These modesl are really not good at instructions like: Follow the instructurions in file xyz to ipmlment this.

🟢 Here's another problem: I have in my readme not to write comments in code only reference readme sections for functional code - because I don't wnat to be paying for comment and code updates and have project bloat. It continues to write commetns even after I have alrady had it clear out comments and told it to operate this way and logged the mistake numerous times. 

🟢 Oddly enough as soon as I published some thoughts about all of this on X my network got cut off, all my sessions ended, and I had to reconnect and start over.

🟢 I have the model track it's mistakes and increment plus on eevery time it makes a mistake. What is bother me is that the model is logging the mistake + 1 like 4 becomes 5. THen it says "but wai thte count is already 5" and then it changes it to 6. That feels like there's something between my prompts and the model or a threading error or something. What is causing that?

6/9/2026 9:28 PM ~ back to testing

🟢 The menus are still messed up. I asked to insert another menu and it randomly changed the headings which I did not ask it to do. If I don't copy and paste the UI it can't figure out what menu comes next. It randoly names things Remove or Delete incosistently. It can't figure out what "Move this option to the next menu after they select x" means. It can't figure out "Move this menu to the x menu (matching banner above menu). It can't seem to understand the consitency of other menus and carry that consistency forward. Everything is multuiple painful prompts. But it's still less painful than manually updateing all the requrirements, xml and glue code to make this all work. That said, I think I am going to have to go in and manually create what the UI is suposed to look like for the menus in the readme because I think that will be faster. I'll have to revisit all that. But add/remove things in config is working. it's jsut a mess to navigate.

🟢 Just realized needs to work diff than depoy project; Need source profile and role profile. Then look up Account, ou, root IDs if exist. Can get MFA serial and all that from the configured profile. Otherwise the user has to specify the aws mangemnt account number like I did in the deploy project. Either way. Or give the user the option to create the role profile. I'll review this all more later. need to get somethign else done. 

🟢 Not following rules for comments again. Adding bloat to project that is already in the readme.

🟢 The model really DOES NOT want to follow rules related to role assumption. I have a third party project and it's like a little kid pretending it did not hear what I said and skiping ahead. I said do exaclty what the other project is doing a bundh of itmes. Then I had to expicitly say copy the section of the readme and copy file x into yoru project.  Now it's writing too much text again for something tha tis not coplicated at all.

🟢 If the user enters a new role profile use the assume role script to assuem the role which should then have the user fill in the necesary role profile info.

🟢 Throw an error if a profile is selected but has no MFA as the role trsut policy requires MFA.

🟢 If the role profile is set ask the user if they want to populte the IDS (org id, root id, etc.)

🟢 Tell the user the ids are optional and can be filled in when deployed.

🟢 If no account or profile don't show the ARN.

🟢 If management account and role profile name are selected calculate the ARN from that.

🟢 If the profile is selected set the ARN from that.

🟢 Let the user select from list of CLI profiles for the bootstrap role.

🟢 Make the copying of default envionments optional if the user wants to build all from scratch.

🟢 Let the suer select the mamangement enviroment from list of enviromnents or display no enviroment sconfigured.

🟢 And finally at 11:29 I can delete an orgnization in the configuration which is what I thought I'd do in two minutes at 9:29 PM. Ugh.

🟢 Messed up banner for a menu. Added single banner printing file for consistency and all bnners use it. Then I realized for consistency that should be in the menus project so moved it over there and had all projects reference it.

🟢 50 tries later got it to show me three menus with the correct menu items and had it update the readme.

🟢 So the model/agent decided to randomly chagne the menus around so I'm putting them back again. This is getting so ridiculous. So I have each menu in an XML file nad thay all use shared menu code and have exactly what they shoudl look like in the UI. So I say insert anew menu. Easy. Add anew XML file. Change the parent on two files to insert the new menu. IT CANNOT get it right. What the heck is so hard about menus?

🟢 Here's how bad Anthropoic models are at Linux pemrissions. It took me weeks to get these permissions right with tons of testing. The group gets read only permissions. THe project owner gets write and EC2 user. So to "fix" this problem it wants to give the project group write access to all projects, completely destroying my sandboxing. NEVER TRUST ANTHROPIC MODELS TO WRITE LINUX PERMISSIONS WITHOUT TESTING THEM. 

🟢 Still fixing scripss referencing q after was renamed to Kiro. Please don't rename products. Broke some premissions and had to fix that and was very difficult for the agents to fidn the problem. Wasted TONS of tokens. ANTRHOPIC MODELS ARE REALLY BAD AT LINUX PERMISSIONS. 

6/9/2026 2:49 PM ~ testing configure organization

🟢 rename projects because it's not really org vs rquirement its -bootstrap -configure -deploy -drift. my framework has a way to rename projects.

🟢 Repeated analysis and not following instructions and not reading readme mistaeks

🟢 Have to repeatedly tell it how to behave which is the first three lines of the reqs

🟢 Had to remvert comments again as told it only to add section headers to reference readme in reqs which it ignores.

🟢 fix rquirements in menu project to new format and add requiements to add /c to any manu to go back to the prior menu. The requirements coudl not be completely put into the menus project because of project specific state changes in projects using the menu code, so had to ipmlemnet that in other projects and provide usage instructions in the menus project.

🟢 organization wide configuration moved out of environment (now deployment) project is loading proroplery. Will test editing it later with a test org.

6/8/2026 9:13 PM ~ had to do other thigns today not going to get much done.

🟢 Finally got bootstrap and env (deploy) project in sync and filled in missing complicated reuquirements after going in circles to get the agent to write them in a sipmle way. It was giving me a lot of convoluted nonsense. Maybe the answer was in there but it was so noisy I just didn't have the energy to sort itout. I told it to write the answers in 8 lines or less in my requirements format and fincally got all the correct info in the orchestrator readme explaining how it shoudl work and had the other project reference that. Even after checking both project's code the env project said everything was wrong when a file path was wrong. Finally I told it tha the other project was fixing the file path and it figured that out. Removed a lot of unnessary comments wasting tokenas and told it to refernce the readme at the top fo th efile only except for variables. Defining what each veraible is for is useful. I still thing ther eare extraneous comments in readme but will deal with that - and test it - alter.

🟢 removed dead code in deployment project and revised to work with org config and bootstrap project...untested.

🟢 Fixed requiremnets and mistakes to a less wordy format; added file names and file modes to requiremenst where approprate and role names for deploying resources

🟢 Yeah this is sketch. Somehow while making edits to readme the model wrote a requirement to give itself an exception to not touch credentials or do anything with them because they are handled by a project dedicated to that purpose which has been reviewed a bunch of times - and gave itself an exception to read AWS credentials for the CLI. Luckily I require MFA and an specific IP address to use those credentials. Yet somehow I reviewed that shared project and some code was added at some point to read credentials in an insecure way. I'm sure that wasn't there before. I haven't edited that project. What?

🟢 Fixing the same thing AGAIN. The org project is trying to directly interact with teh env project instead of keeping it's code sepaate. It did not follow instructions and changed the readme so I'm fixing that now.

🟢 Too many mistakes to log here. First the model told me to do something blantant not allowed in its readme. Then it can't figure out how to write accurate instrutions. It's not correctly file name in README when strucuture has changed. We are fixing config moving from env to org because it's org wide and the model keeps screwing up. It update the file and left hte new config out of the readme. It's not doing what I ask right away or the way I ask. *sigh*. I can't spend all my time logging all of this. The models are not good at complex cross project architectures. But if you give them all the code in one project they mess it up. I'm having to be very explicit and ask it questions to ensure it has analyzed things correctly and repat myself a lot right now. But it eventually gets it. Switching back to 4.6 to see if it does any better.

## 6/6/2026 4:406 PM

🟢 Moved organization wide cnofiguration items out of env to org.

🟢 Bridge Deployment menu through orchestator to Environment project

🟢 Interesting thing just now. Model was trying to write some test code and it wrote an eternal loop, ran the code and got stuck. So what if that happend inside an AI agent running autonoously. Would it crash?

🟢 Added suport for account types.

🟢 Restructure bootstrap menu - Configure organization, deploy, drift management

🟢 Add drift detection report project. Finds resources that do not align with organization configuration.

🟢 Another review of the enviroment resources deployment project to make sure it uses the shared menu code removed another batch of code

⭐️ ~ LOC removed 100-150

🟢 Added to readme to one project (need to add everywhere) not to add specific requirement numbers in code since they change. That's just a waste of tokens to try to keep taht up to date. Long comments also waste context. I told it not to repeate requiremetns in files and only reference requierment headers. I also changed the requirements to have section headers like ### Whatever and a list of numbers 1, 2, 3, 4 so I cna avoid having to update the whole reuqirement section numbers if I wnat to add a new reuqirements section. 

🟢 Add configure step to menu instead of displaying it before running enviroment deployemnt. Insteada of showing it every time and asking if ok can choose to configure/check it as needed. Also works better in the flow and keeps the control of that with the environment project. Had env and orcheatrator arguing about how to fix it.

🟢 So I had to have two agents argue with each other about 10 times until I could get them to agree on how to handle complex menus. HOpefully it works. Test tomorrow. Now there's a way to manage Environment Types, Acocunts in Environment Types, and items that appear in the list of Resources that you can deploy to an environemnt of a particular type.

🟢 The agent/model/whatever doesn't read the full readem or all requiremetns even when my instructions say read it and then read it again to see what you missed. I tried to create prompts to fix this. Nothing works. Just have to reprompt and create tests which I've added to all projects - but half the time the agent messes up the tests so we'll see how that looks when I check the code.

🟢 AI is really, really bad at menus structures. Have I said that already? Yes. Yes I have. Still fixing things. I mean the complex relatinships with menus that drive other menus and all the data involved not just a simple menu or y/n prompt. I may have a solution but still testing...

🟢 Ability to Modify Environment Type account list

🟢 Independent generic menu project to handle gereric simple or xml driven menus in a way that any bash can use it.

🟢 Bootstrap orchestrator project; completely segregated code so env project does not depend on org project and vice versa. Both continue to run independently as needed until I convirm everything is working correctly.

🟢 Tested integration and deployments work from new menu project. But the menu project is not generic enough...

🟢 Initial review of xml parsing code found numerous errors which have been fixed and tests written to prove correct. Still needs more testing and review but better. Now the two other projects can't introduce security problems into xml parsing code. Just need to make sure they only use that code and don't end up writing their own xml parsing code which happens.

🟢 Single shared xml parser code in separate project. Like I've written about on my blog AI is non-deterministic. So I had two software projects using xmllint in two completely different ways, one of which was kind of sketchy and possibly insecure but I'd need to look into it more. I got one of the projects to write the code in such a way it will work for both, but the risk is that now the one project with control of the code might break it so it doesn't work for the other. So the first thing I'm going to do is put bash-xml-parser into it's own project both can use but not change. Along the way I'll try to ensure that the logic in that project is complete and secure and can work for all new future projects so I don't have XML parsing being done every which way and don't have to spend time on that. The readme in the XML parser project will say how to use it. Multiple projects reviewing and using it will tell me if there's anything wrong with it. I have a framework that lets me spin up a new project, create a github repo, set up the custom agent in a minute and customize all the Kiro settings along the way if I want to so I just use that each time I want to set up a new project. I do not give me credentials to the agent or third-party tools. All deterministic scripts I control.

## 6/6/2026 1:46 AM

🟢 Cleaned up ugly code to make it more maintainable and better ogranized. Result:

So very roughly: ~335 added, ~215 removed, net +120 lines — but spread so that run.sh got much smaller and the logic moved into small focused 
files.

🟢 Created a new project with a mechanism to define an org name, configure all the environments form a list of environments with default recommendations such as management (one and only one), kiro management environment, work environment (where people log into ec2), web environment (no ec2 logins), DNS, test (for test infrastructure like burp and other instances used for testing not development), etc. So they can add a list of environments with a name and a type and then the appropriate resource list shows up for each environment type so they can deploy those resources to the environments. The mapping mechanism helps add/remove new resources easily to menus and thereby create any grouping of resources that can be deployed in an environment.  It works the same as existing code but the menus are actually written properly and configurable via XML which Anthropoic models like. Then my new project can source all the files that do the actual deployments via the files in the bootstrap project. And the bootstrap resource files can't mess up the menus and vice versa. Also this would break everything if I did it in one project (as it did before) only worse - I wouldn't be able to manage some existing resources. So what I have now is the ability to manage the existing resources with the old menus until I get the new menus working and the environments aligned. I added the organization deployment and now that can be read from the organization name stored in the xml file and the environment names match OUs. I'm not doing any nesting here because I found that complicated for my small org but could easily add a parent node to the environment xml files and have them reference each other. More testing is needed but this should resolve a bunch of issues and make it harder for the creation of resource fields to get so messed up and keep menus in tact and consistent.

6/5/2026 5:04 PM Starting now...have to login and update some settings each time I start - something I hope to automate n the future. It's related to some stringent security controls because I'm a super security nerd.

🟢 I know that all the menu problems I'm having are related to this: my code base is too big. I shoudd have a separate code base for the menu structure and move all my resource stuff into separate projects. And maybe I will at some point. But for now the fix is to keep it as clean as possible. This is an issue not that was fixed and maybe a future feature but noting it here that I am aware of it and what the problem is.

🟢 I start out by thinking about the problems I need to solve next. I'm thinking about multiple tings at once here. I want to set up a test organization to test this script end to end. What domain will I use? I can test my domain registration piece. But I am thinking about where the domains are registered. I don't want those domains to ever get deleted. I could register my test environment domain in an account I don't plan to delete later in a separate organization. I'm thinking about a separate Domains environment just for that to lock in those domains and ensure an account does not accidentally get closed down with my domains in it, which just happened. It was only test domains in a domains environment so if I lost them no big deal but still. I think I'm going to move domains into their own environment. Then I have to deal with all the related implications. But I can put an SCP on that domains environment. And I probably want a prod domains and test domains environment. So really domains is a whole new environment type. That environment test locked down with an SCP to deny all unless I'm actively making a domain name change. So that's my next change. Region specific problem: I have some environments were I only want to run jobs in a particular region. But I have to put the auth in a different region for various reasons. And Kiro only runs in us-east-1. So I have all these one-offs. So really I want Kiro in it's own enviornment to manage the subscriptions and such. And then I need cloudfront in it's own region because certs for cloudfront only work in us-east-1 and I might need to allow cloudfront in more regions than my other apps. So really the allowed regions is per environemnt. So i have the org regions allowed at root. Then I have env allowed regions at the environment level. Environment specific scps. Blah blah blah. I rearranged the readme and added some new organizations to solve some of those problems. We'll see how it works out.

🟢 Along with this I'm thinking about a configure organization script...added to run list.

## 6/4/2026

🟢 Fixed various things, added organization adn all features step, tested, verified and in between tested ACM step and dosn't work. Told the model to add code to check status of domain and hsotd zoen befoer installing the cert. FINALLY. I kept telling the agent to gather any and all info to troubleshoot the problem and it couldn't figure it out. Finally i rant the move hosted zone step again which has all the output about what it is moving. I gave that to the agent and it figured out that the domain was wrong in a config file. Added another check to display teh domain and the hsoted zonesin the accout and tel the user if no matching hosted zone. Should have made that problem obvious.

🟢 Syntax error after fixing menu which goes to prove the models are dumber at this time of night (it's jsut after midnight ET). I rarely see blatant syntax errors.

🟢 The model seems to just deteriorate the later it gets. I just told it steps were missing from a menu. It gave me this lengthy explanation. I told me to rerun the program without fixing anything.

🟢 Tryign to findinstance code that was working does not work anymore. when it renamed the step it must have changed something related to the instance name or query incorrectly. I never told it to toucht that code or anyting aobu the instance code only rename the step so not sure why it did that.

🟢 When I told it to rename all the files related to a step it missed the verify file. I asked it multipel times to fix that label and insted of removing the stuff in parenthesis like it did before it changed Deploy to Create which is not what I wanted. I said "this is still not right" and it didn't check back to see what that meant. Obv I can be more explicit.

🟢 Still hasn't gotten fixing menu labels right for something used across all resource steps.

🟢 Running verify steps for ram shares and VPCs were not properly shared to traget accoutns in all cases.

🟢 At some point it switched back to 4.6 don't know why but anyway whateer it was tried three times to get the label on a menu item right and can't figure it out. Tried to fix the backslash issue multipel times as well.

6/4/2026 9:03 PM Going to give automode another chance here's how it went

🟢 I have an SCP designed to only allow an enviromment to taek actions or access it's own resources. So many complicates with that. The orgpaths condition doesn't work consistently across all resources for one thing. I had to open it up to allow the org IPAM since I can't create an environmnt specific IPAM. And now for the AMIs. I am trying to launch AMIs and I have to make an exceptoin for Amazon AMIs. I don't wnat to allow all, only AWS AMIs. What I would rather do is have a way to pull those AMIs inot my own repo in the env and use that. BUt that action in itelf might require an exception. Maybe I could put that in a separate env to access external resoruces or something. But anyway fixed for now the way it is and think about it more later. I do not want to have ServiceLinkedRoles in my account as much as possible since they are not subject to SCPs.

🟢 When i asked if it read the rules it interpeted that as reading the mistakes at the bottom of the readme; and by the way I haven't really been using mistakes much lately. Not sure how much is helping.

🟢 Saying it cant run an AWS command which is true its supposed to write it in the code not run it.

🟢 It doesn't follow rules in auto mode tried to write to another project.

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

## 6/3/2026 

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

## 6/1/2026 - 6/2/2026

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

