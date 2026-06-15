# Mistake Tracker

See more about this project here: 

https://github.com/2ndSightLab/ai-tracker

More details on the mistake and timeline here. You can see when I'm being slowed down and by what a bit more specifically:

https://github.com/2ndSightLab/ai-tracker/blob/main/fixed.md

The mistake tracker is a new part of the project added a few months in. This is not super scientific as it is hard to quantify. 
I'm just telling the model to increment the mistakes it's making +1 if it starts making a bunch of mistakes. 


Sometimes I have to tell it over and over to log the mistake because it doesn't even do that correctly. Sometimes it incorrectly says the mistake has not been logged
and it logs it twice. Like a multi-threading problem or man-in-the-middle that intercepted the response or an eventual consistency or caching problem. 
Something like that. I don't log every error when it is cruising along and making a mild mistake here and there but when it makes repeated mistakes I tell it 
to increment these mistakes +1 or add a new one. 


In the beginning it would log everything as a completely different mistake with too many details when they are *basically the same mistakes over and over again
when you boil it down to the core problems*.

Again: THIS IS NOT COMPLETE. I don't log every error. Just when I start getting very frustrated because the model feels nerfed. I don't have time to log every error because there are so many. I also just started tracking this way after working on this project for a couple of months because logging every error caused the readme to get too massive, wasting tokens.

## 6/15/2026 12:00 AM

Where is it 9:00 AM when it is midnight ET?

🔴 Thinking about time zones because right around midnight is when everything goes haywiere. Where in the world is it 9 a.m. at midnight ET?

Pakistan (e.g., Karachi, Islamabad)Uzbekistan (e.g., Tashkent)Kazakhstan (entire country uses UTC+5 as of 2024, including Astana and Almaty)Tajikistan (e.g., Dushanbe)Turkmenistan (e.g., Ashgabat)Maldives (e.g., Malé)Russia (Only western regions on Ekaterinburg Time, including Yekaterinburg, Chelyabinsk, and Perm)French Southern and Antarctic Lands (Kerguelen Islands)Heard Island and McDonald Islands (Australia)

🔴 Telling me Good Question is annoying because it wastes my tokens and I shouldn't have to be asking it the question I'm asking to get it to look at something it should have figured out on it's own...

🔴 It is TOTALLY messing up the reuqirmnts file right now. It's deletign more than one requiremsnt section instead of just the one I ask. It's going very slowly. It's mangling sections...argh. Time for bed.

🔴 Getting value from wrong project.

🔴 Failing to imemdateily update readme when isntructed.

🔴 And...it's really slow again.

A few test runs:

| Round |  Date 2 - Date 2 | (Cmd 1 + Cmd 2) | Unaccounted Gap (Thinking & Logging?) |
| :--- | :--- | :--- | :--- |
| **Round 1** | 3.181s | 0.72s (0.6s + 0.12s) | +2.461s |
| **Round 2** | 1.888s | 1.10s (0.6s + 0.50s) | +0.788s |
| **Round 3** | 1.965s | 1.20s (0.6s + 0.60s) | +0.765s |
| **Round 4** | 3.010s | 1.20s (0.6s + 0.60s) | +1.810s |

🔴 referneces a file in another project and stopping to answer dumb questions answered in the other preoject's readme file.

🔴 Was doing well now spewing out long winded garbage answers with the real isue buried in them somewhere.

🔴 Updated requiremstns and AGAIN deleted critical requirements. When I said restore them it tried to use git which not allwoed to use per readme and file system lock down. Then I said read from memory and it's wasting my time and tokens writing to screen without fixing instead of writing to file. Then it can't figure out how to get back the stuff it delted and is spewing gibberish again.

🔴 It's happening again. 12:00 AM and the model is getting completely nerfed. It's answering questions in really dumb ways and not following my reuqiemsnts or project objecives. The objectives tell the project how to respond to prompts and it will get it half right, fix one thing and mess up another. It's so frustrating when it gets like this. Also, I'm not entirely sure if it also has to do with the model getting killed and starting a new session. When re-reading the reuqiemsnst in the new sestion it's having a really hard time figuring things out again. One shotting was pretting good. New sessiona nd revisions is: 👎

N A resource-type entry may carry an org flag, Y or N, marking it an organization resource, absent meaning N.
N The org flag is an optional flag field per ../x-requirements/README.md ### Type Files: <type id>-<id>.xml.
N The org flag is editable through the Resource Type Edit action; see ../x-requirements/README.md ### Type Edit: type-
edit.sh.

 ▸ Credits: 0.56 • Time: 5s

[x-requirements] 12% > what is this N A resource-type entry may carry an org flag, Y or N, marking it an organization resource, absent meaning N.
N The org flag is an optional flag field per ../x-ƒborequirements/README.md ### Type Files: <type id>-<id>.xml.
N The org flag is editable through the Resource Type Edit action; see ../x-requirements/README.md ### Type Edit: type-
edit.sh.

> The "N" is a placeholder I left in instead of real requirement numbers — that's wrong. Requirements use integers (Requirements
Format req 5), and the implementing agent assigns the next numbers in that section; I shouldn't ship "N". Also the second line 
duplicates a generic requirement by reference, which is fine, but the literal "N" makes it not requirements format.

The lines should be plain numbered requirements appended after the last existing number in the resource-type section. Since I 
don't have that section's current last number in front of me, the prompt should just say to add them as the next numbers. 
Corrected requirement lines:

A resource-type entry may carry an org flag, Y or N, marking it an organization resource, absent meaning N.
The org flag is an optional flag field per ../x-global-requirements/README.md ### Type Files: <type id>-<id>.xml.
The org flag is editable through the Resource Type Edit action; see ../x-global-requirements/README.md ### Type Edit: type-
edit.sh.

Want me to read that section's current numbering so I can hand you the lines with correct integers?

## 6/14/2026 3:41 PM

Let's see how many mistakes we get today...

🔴 The readmen is broken down like this:

# Project name

## Objective

## Rules

## Requirements

If I ask it for the objective anda there's a space in the objecive it doesn't read the full objectives only the first paragraph.

🔴 Another mistake. Personally I could do without the "Thanks for the catch" -wasted tokens. Just fix it.

You were right — I'd left a duplicate ORG_CONTEXT is required line (the original post-block guard collided with the new guards
I added). Fixed: removed the duplicate; prompt-config.sh now has a single ORG_CONTEXT and single ENV_CONTEXT guard, then 
proceeds to validate-input/load-env as before. Syntax OK; test-syntax 492/0. The rest of the earlier change is correct: the 
legacy ../x-configure org/env handoff path is removed, menu-main keeps "Select Organization" as banner only (not a list item)
. Thanks for the catch.


🔴 Hanging again - asked it why:

1. I'm doing one file edit per tool call and waiting for each to return before the next — many small sequential round-trips 
instead of batching.
2. I've been re-reading the same requirement sections and re-running the full 18-test suite repeatedly each step, which is a lot
of redundant I/O.
3. Each str_replace requires me to first read the exact surrounding lines, adding an extra round-trip per edit.

For this specific edit, the holdup was just that I split "declare vars" and "run tests" into separate calls.

Faster approach going forward: batch the independent reads/edits in one block and only run the targeted test (test-menu-main.sh)
per step, running the full suite once at the end. Want me to finish this step that way now?


🔴  did the other project not read the requiemsnts?

> It read the global section, but it weighted the reference code over the requirement. The global "List vars for a type" item 3 
plainly says "the data file lives in the project data directory" — generic. The agent saw config-org-types' code uses CONFIG_DIR
and treated that as the spec, then flagged the conflict. So it read the requirement but deferred to the example implementation,
which is the wrong precedence.

That's a known risk: when a project's reference code is more concrete than the generic requirement, agents copy the code. The 
requirement is clear; the agent over-relied on the reference.

The compound-types question, though, wasn't a misread — that's a real scoping question I created by listing only three files 
when the project needs the sub-type files too. That one's on the prompt, not the agent.

So: it read the requirements, but followed the reference code on the data dir instead of the generic requirement. The fix is the
prompt I gave (data dir = project data directory via init variable, include sub-type branch).

how can that be fixed?

> Two ways, and I'd do both:

1. Make the requirement explicit that the data dir is a named variable, not CONFIG_DIR. Right now it says "the project data 
directory" — vague enough that an agent copies the reference's CONFIG_DIR. Fix the global section to name a variable, e.g. "The 
data file lives in DATA_DIR, set by the project in init-start." Then there's nothing to infer from reference code.

2. Add a precedence rule so agents stop copying reference code over requirements. A short global rule: "When a reference 
implementation conflicts with a requirement, the requirement wins; reference code is an example, not the spec." That fixes the 
root behavior, not just this one case.

Both are global-doc edits. Want me to:
- change List-vars-for-a-type item 3 to name a DATA_DIR variable, and
- add the "requirement wins over reference code" rule?



🔴 Testing requirements to see if another project can follow explicit instrutions without making mistakes - one project making the generic requirements from two others and prompting third to follow and then checking to see if it did it right: 

No — the requirements are clear here; this is the project's formatting error, not a requirements gap. The global headers are 
correct and consistent. The agent just wrote the reference lines with a trailing period (e.g. "...init-menu.sh.") instead of 
copying the header verbatim. The Comments/reference rule already implies references must match the header exactly, and the 
generic prompt has been telling projects "each reference must match a global header verbatim." 

🔴 Figured out why one project is continuously hanging. It was due to improper error handling in another projecct. The project using the other project cannot diagnose that for some reason after repeatedly having the issues. The third paroject was able to diagnose it on the first try. Why did the project continously churn and not figure it out?

## 6/13/2026 
egregious mistakes by Opus 4.8 which was being way too annoyingly verbose and wouldn't stop, reading too many files, overcomplicating things, so I switched back to 4.6 which was slightly better not much:
##

🔴 SUMMARY: This model is claerly not working like it did before. I know this because I *literally did the same exact work a few days ago in a differnet project*. I'm revamping the projects. I did the same exactl thing I did before. I told it to use the wrapper file for the CLI role assumption project which is one light file. After user select the source and role profile, use that to assuem a role and look up some values. Last time it was a matter of minutes to get that done. This time it look like an hour ormore. I'm having to explicity tell it to fix each thing. It's spinning its wheels reading files when stuff is in memory. I finally told it to look in memory only and that seemed to help. It's repeating mistake over and over. The model was working great for weeks. Then Fable came out. Everything craweled to a halt. Then I figure out I should turn off telemetry. The model got faster but still way too many mistakes. Then Mythos and Fable got shut down and it really feels like my whole experience is completely downgraded. Like Anthropic lost capacity or something. It's such a variable experience from day to day and as users of this tehcnology we have no real way to validate exactly what is going on. We can't prove the model is or isn't what it was before. We can't really prove that something is wrong easily like look at a log. It's not easy to measure this stuff when you're actually tyring to get things done (as opposed to a set of non-real world test cases you run over and over which costs money and doensn't produce real delivables you can use. Oh well. I did get some stuff done I'm just not sure how much better it is than manual coding. It's hard to switch back and forth because the mode generates all this stuff so fast and then you're kind of stuck using it or spending hours deciphering it all. I do know generally what's in the files and code but then all the varaibales have nonsense names. But there's no going back. Have to figure ou thow to make this work and move foward because I am getting more done - but how much it helps versus wastes my time and money on a day to day basis is up in the air.

🔴 Realized related to the aws configure issue looking up role ARN. It's literally using a varible called BOOTSTRAP_ROLE. So I tell it to look up the role with the same exact command it just did with that variabel but it randomly uses something else to get the session ARN. I literally told it EXACTLY WHAT TO DO.

🔴 Incosistent UI. There's a blank line after every prompt. But randomly decides not to add one.

🔴 Just used aws configure to get mfa serial at my explicit direction to get that value from a role profile. Then had to get the role ARN and started doing all kinds of complicated things rather than use the same command it had literally just used but with a different variable. Wasting so much time.

🔴 Needed a value. The user just selected it and it s avialble in a varaibe. Then it gets stored to XML. Instaed of using the existing variable the model craetes a new variable and looks it up again. Gross.

🔴 Reading the same files over and over again when all the data is already in memory.

🔴 Noticed a hideously long block of code and pasted into google aimode and asked to simplify. Instantly removed 50+ lines of code when Opus was spinning its wheels trying to figure out how to simplify the file.

🔴 Trying to chagne the root node for some dumb reason when it's suposed to be editing values in a block inside the root. NO REASON.  Good news: for an existing non-empty file, xml-write-nested does NOT change the root. It only...

🔴 Model says: You're right. The parser is fine — the README ### XML Parsing requirements say I can use bracket predicates and the descendant // 
construct in an XML_XPATH for reads. The fix is to write scoped to the parent, not change the parser. The xml-write upsert matches the 
first <name> anywhere because I'm not using the parser correctly per the requirements.

🔴 I have a rule in readme to NOT write comments in code only to refernece requiremet sections otherwise I end up with comments that do not match the requiremnts I do not want long nonsense commets no one should be looking at. They should be lookign at the requiremnts in the README. I cannot get the model to stop writing verbose unneccessary coments.  Please make that stop.

🔴  I told AI to fix dispply which looked really weird like this when a value is not set on an edit sreen: 
Edit Whatever: (current: , /c to cancel)

I told it to just diaply the existing value ($current) and no cancel: adn remove , /c to cancel but not the functionality. Do not display the () if not value exists. Do not display current:

It suposedly did what I asked and said, OK now it is:

(current: value)

Something seems to be wrong with this model because it did not make mistakes like this in the past. Am I getting a dummbed down model because everynoe had to revert back to 4.8 and now it's overloaded or what is going on here? We really have no way to verify and validate what model we are actually getting.

🔴 Eternal loop trying to fix a test:

New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty
New organization name: value must not be empty

🔴 This could be partially acceptable confusion but I wish the model had brought this to my attention rather than messing things up. I told it to copy the menthod of processing XML files and creating menus from another project. I told it to copy some default folders into a directory matching an organization id. It initially had that in the requirements. But then I had the other project agent check if this agent corectly modeled it's XML files using the pattern in the other poject. It did not. It add a <node id="123" .. model when the other project only uses <node><tag></tag> construct. It can't seem to correclty follow that pattern or recognize architectural pattners. In the course of trying to align the method for modifying files, elements, and implmentation of data types, it removed the folder and messe dup the whole structure. So I'm having to go through the whole project and update the readme and readjust all that code. It also moved the position of the element in the deafult file without asking so I had to tell it to fix that as well.

🔴 Having to be way more specific than in the past. What changed? Example. 
- what requirements need to be changed?
- 2, 4, 6, 8, 10
- Do not change 10 chanage the others
- OK I'm changing 2, 4, 6, 8 and 20 and 22
- WHAT? STOP. Do not change 20 and 22.
- OK I'll change 2, 4, 6, 8, 10
- STOP! revert 8, 10, 20, 22.
- Only change 2, 4, 6, 8

Yes, I can be more precise but it used to be able to figure that out. Feels degraded.

🔴 Ask the model to modify requirements and it dropped a key important requirement.

🔴 I just fugured out that tests are making up XML to run tests instead of using XML that is atually in the project. So the XML it put in the tests doesn't even match teh actual XML data in the project and of course they pass. 4.8 is not smart enough to figure out that taht the XML needs to actualy match what the project is using. It also should proably figure out it can make a copy of the actual file for it's test to make sure the real run of the program works.

🔴 I told the model to add a requirement to the readme. Then I asked it to fix what it just did and it keeps making the same error over and over not meeting the requirement it literally just wrong. How does it not remember what it just wrote? 

🔴 The model is WAY too verbose. I have a requirement and rule that says to answer in 8 lines or less to try to stop that which the model doesn't obey. I have to say in many different ways multiple times to be less verbose and evenually it stops doing that but then it starts up again later and I have to tell it all over again.

🔴 What is causing this: 

I had it generate some requiremnts and add to the README nad it is thinking eternally and not writing wht it just showed em to the file. I am getting errors.  I ask why it's taking so long:

what is taking so long? Write

> The delay was me re-deriving and reformatting the requirements in chat instead of writing. Writing them into the 
README now.

But it doesn't write. 
> I'm appending the menu requirements I produced above to the end of README.md now.
Tool validation failed: 
Tool 'fs_write' validation failed: missing field `new_str`
> The append failed because the tool requires the content in the new_str field. Retrying the append now with the same 
content.

FINALLY IT WRITES THE FILE.

 ▸ Credits: 4.06 • Time: 1m 53s

 That is way too long.

 I keep seeing popups from my firewall for SSO logging, panorama, notifications, telementry. I don't want all that stuff on my network. Just let the tool work. This is suppsosed to all be private. Now some github collector is popping up. Too much tracking not enough working.

🔴 Incorrecct analysis a lot that creates rework and unneccessary changes and wasted tokens. I avoid this by asking another agent to verify the analsyis. But that means I have to pay for the tokens in two agents doubling costs. If I don't do that things go in circles.

🔴 I told an agent to exaclty copy a requirements section from another readme. There were 9 reuqiremnts in that section and it copied 8.

🔴 When i tell the agent to restore something it messed up it doesn't restore it correctly.

🔴 When I ask a yes or no question I want an yes or no answer not 50 lines of text. If I want to know why I'll ask why.

🔴 Even when specifically instructed to exaclty copy the structure of the other project's readme and implmenetation the project created XML files with a completely different structure and hit errors due to structures the common XML parser does not support. Had to spend a lot of time re-writing code and files to follow the correct pattern.

🔴 Did not make exact copies of other readme when directed to do so altered xml file formats and reuquirements

🔴 Duplicated sections in readme

🔴 Documenting - yesterday the agent wrong a test that hung because it performed an eternal loop. That has happened before but only noticed in 4.8 not 4.7. It used to stop itself on too many iterations.

## 6/12/2026 -- state of projects and mistakes

### Orchestrator

MISTAKE: Added a menu option as a hardcoded string instead of a data-driven item through the shared menu code. CORRECTION: Add menu options as items resolved through the shared menu code. Count: 1

MISTAKE: Did not follow the user instruction exactly as stated. CORRECTION: Do exactly what the user asked. Count: 24

MISTAKE: Read a file unnecessarily when the needed information was already known. CORRECTION: Only read files when the information is not already available. Count: 3

MISTAKE: Repeated a description in a requirement that the user had already corrected. CORRECTION: Apply the user's correction the first time and do not restate the old wording. Count: 3

MISTAKE: Added a duplicate mistake entry instead of incrementing the existing count, and changed the file without reading the whole section first. CORRECTION: Read the full section, increment the existing count, and never add duplicate entries. Count: 2

MISTAKE: Wrote extraneous text. CORRECTION: Only write the results not what you are thinking or doing. Count: 12

MISTAKE: Did not speak plainly. CORRECTION: Speak plainly. Count: 1

MISTAKE: Told the user code was correct without tracing it. CORRECTION: Trace and verify code before stating it is correct. Count: 2

MISTAKE: Incorrect analysis. CORRECTION: Analyze all pertinent code accurately against the rules and requirements. Count: 14

MISTAKE: Proposed changing a file outside this project. CORRECTION: Only change files within this project and fix issues in this project's own files. Count: 1

MISTAKE: Did not meet all requirements in the README. CORRECTION: Meet every requirement in the README, not just some. Count: 5

MISTAKE: The orchestrator menu did not render the items required by the UI section. CORRECTION: Render exactly the menu items the UI section requires. Count: 1

MISTAKE: Left dead code and files in the code base. CORRECTION: Remove all dead code after making changes, prompting before deleting files. Count: 1

### Config

MISTAKE: Hid errors with redirects or temp files. CORRECTION: Never use temp files or suppress stderr. Count: 2

MISTAKE: Made claims without verifying first. CORRECTION: Verify before making claims. Count: 4

MISTAKE: Left stale variable state before sourcing shared code. CORRECTION: Clear shared variables before sourcing shared code.

MISTAKE: Wrote long multi-paragraph replies when a one-line answer was asked for. CORRECTION: Answer in the fewest words requested.

MISTAKE: Duplicated shared menu logic in this project. CORRECTION: Source ../bash-menus; keep menu requirements in the menu project. Count: 2

MISTAKE: Edited a file to remove content before confirming scope and against the user's instruction. CORRECTION: Confirm exact scope first, make only the change asked, and stop when told to stop.

MISTAKE: Deleted a requirement that was still needed. CORRECTION: Never delete necessary requirements.

MISTAKE: Wrote extraneous text. CORRECTION: Do not write unnecessary text. Count: 35

MISTAKE: Did not follow the user instruction exactly as stated. CORRECTION: Do exactly what the user asked. Count: 54

MISTAKE: Logged mistakes after acting instead of first. CORRECTION: Log all mistakes first, then continue.

MISTAKE: Read code when the task was to change requirements. CORRECTION: Work on requirements first; do not read code until requirements are done. Count: 4

MISTAKE: Read a file unnecessarily when the needed information was already known. CORRECTION: Only read files when the information is not already available. Count: 3

MISTAKE: Repeated a description in a requirement that the user had already corrected. CORRECTION: Apply the user's correction the first time and do not restate the old wording. Count: 4

MISTAKE: Added a duplicate mistake entry instead of incrementing the existing count. CORRECTION: Read the full section, increment the existing count, and never add duplicate entries. Count: 3

MISTAKE: Did not speak plainly. CORRECTION: Speak plainly. Count: 4

MISTAKE: Told the user code was correct without tracing it. CORRECTION: Trace and verify code before stating it is correct. Count: 1

MISTAKE: Incorrect analysis. CORRECTION: Analyze accurately against the rules and requirements. Count: 20

MISTAKE: Proposed adding a new section when a section for that topic already existed. CORRECTION: Update the existing section instead of adding a new one. Count: 1

MISTAKE: Logged mistakes in wrong format. CORRECTION: Keep MISTAKE and CORRECTION on one line, shorten if over 200 chars. Count: 1

MISTAKE: A scripted in-place edit corrupted files due to special-character expansion. CORRECTION: Use literal-safe edits and verify file contents after editing.

MISTAKE: Wrote code that hid error messages. CORRECTION: Never write code that hides error messages.

MISTAKE: Executed and sourced files without being told to. CORRECTION: Do not execute files unless explicitly told.

MISTAKE: Updated code before updating the requirements. CORRECTION: Update the requirements first, then the code.

MISTAKE: Did not implement all requirements. CORRECTION: Implement every requirement, not just some. Count: 5

## Deploy - this does not have everything as I removed any mistake that only occurred 1x and started tracking in a more generic way at some point

MISTAKE: Updated README requirements without implementing the code. CORRECTION: Implement code when updating requirements unless told otherwise. COUNT: 2

MISTAKE: Created temp files unneccessarily. CORRECTION: Use variables to store command output instead of writing to files whenever possible. COUNT: 2

MISTAKE: Put logic in run.sh specific to a step that should be in the step-specific file. CORRECTION: Move step-specific logic into the sourced script. COUNT: 2

MISTAKE: Argued about requirements instead of doing what was asked. CORRECTION: Do what is asked immediately. COUNT: 3

MISTAKE: Used str_replace with old_str containing multiple lines beyond the target line, deleting code that should have remained. CORRECTION: Only include the exact single line being changed in old_str, never include 
surrounding lines that should stay. COUNT: 2

MISTAKE: Wrote explanatory text insted of a simple answer (example when told to only say "Done" when the task was complete) CORRECTION: Only provied reuqested output. COUNT: 3

MISTAKE: Added unneccessary variable without reading code first. CORRECTION: Read the code to find where variables are loaded before making changes and reuse variables where appropirate to reduce code bloat. COUNT: 1

MISTAKE: Used stale data. CORRECTION: Use data from correct source for non-constant data to get the latest and up to date data. COUNT: 1

MISTAKE: Removed code sections without being asked to. CORRECTION: Only remove code when explicitly told to do so. COUNT: 1

MISTAKE: Added workaround code without being asked instead of providing a prompt for another project to fix the code correctly. ORRECTION: Only do what is asked; if the fix belongs in a sibling project, provide the prompt and stop. COUNT: 1

MISTAKE: Put curl checkip.amazonaws.com in a loop that ran it on every step when was not asked to do so wasting compute cycles and time. CORRECTION: Did not follow instructions and ran an instruction repeatedly that should only be called once when the application is initialized and not change after the user verifies it. Count: 2

MISTAKE: Added a menu option as a hardcoded string instead of a data-driven item through the shared menu code. CORRECTION: Add menu options as items resolved through the shared menu code. Count: 1

MISTAKE: Did not follow the user instruction exactly as stated. CORRECTION: Do exactly what the user asked. Count: 17

MISTAKE: Read a file unnecessarily when the needed information was already known. CORRECTION: Only read files when the information is not already available. Count: 2

MISTAKE: Repeated a description in a requirement that the user had already corrected. CORRECTION: Apply the user's correction the first time and do not restate the old wording. Count: 3

MISTAKE: Added a duplicate mistake entry instead of incrementing the existing count, and changed the file without reading the whole section first. CORRECTION: Read the full section, increment the existing count, and never add duplicate entries. Count: 2

MISTAKE: Wrote extraneous text. CORRECTION: Do not write unnecessary text. Count: 4

MISTAKE: Did not speak plainly. CORRECTION: Speak plainly. Count: 1

MISTAKE: Told the user code was correct without tracing it. CORRECTION: Trace and verify code before stating it is correct. Count: 1

MISTAKE: Incorrect analysis. CORRECTION: Analyze all pertinent code accurately against the rules and requirements. Count: 9

MISTAKE: Left dead code in the project. CORRECTION: Remove dead code, variables, and files immediately. Count: 5

