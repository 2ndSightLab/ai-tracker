# Mistake Tracker

See more about this project there: https://github.com/2ndSightLab/ai-tracker

The mistake tracker is a new part of the project added a few months in. This is not super scientific as it is hard to quantify. 
I'm just telling the model to increment the mistakes it's making +1 if it starts making a bunch of mistakes. 


Sometimes I have to tell it over and over to log the mistake because it doesn't even do that correctly. Sometimes it incorrectly says the mistake has not been logged
and it logs it twice. Like a multi-threading problem or man-in-the-middle that intercepted the response or an eventual consistency or caching problem. 
Something like that. I don't log every error when it is cruising along and making a mild mistake here and there but when it makes repeated mistakes I tell it 
to increment these mistakes +1 or add a new one. 


In the beginning it would log everything as a completely different mistake with too many details when they are basically the same mistakes over and over again
when you boil it down to the core problem.
Again: THIS IS NOT COMPLETE. I don't log every error. Just when I start getting very frustrated because the model feels nerfed. I don't have time to log every error because there are so many. I also just started tracking this way after working on this project for a couple of months because logging every error caused the readme to get too massive, wasting tokens.


Here's my list on whatever date this file was last updated for the following projects:


## Orchestrator

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

## Config

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


## Drift Manager
