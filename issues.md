
🟡 For me to fix  🟠 External issue  🟢 Resolved

6/1/2026

🟠  I'm having to redo my Kiro subscription again. I don't like it that overages cost more than the base plan. That means I keep having to delete and create subscriptions. Even though I deleted some subscriptions at the end of the month in teh past they got renewed. The fine print says the rollover is UTC which I thought caused my initial issues. But then it rolled over pre-UTC and I still got billed for a subscription in the next month when I tried to cancel it because I as taking a trip. This whole monthly subscription thing is painful. Some months I need to use it a lot and others not so much. Pay as you go pricing like all the rest of AWS - one of the core principles on which the service was built - would be so much better in my opinion. As of now I have to go in and figure out how to get a new user and subscription set up. The last time I tried to create a new user in a stand alone IDC instance in my AWS account the user jsut sat in pending and I couldn't actually login so I deleeted the whole instance and the whole account. Now I am trying to use my script to redeploy all that but my script broke with all my rejiggering so I'm in this catch-22 state where I have to manually create the IDC and user and Kiro instance if I want to use AI to fix my code and redeploy the Kiro instance and IDC in an automated fashion. The other problem I had was that when I looked at what got deployed by the AI generated code there were weird names and multiple instances or something in my Kiro setup. I need to go back and read the documentation and test out the code in a separate account maybe to figure out what is wrong with what it is deploying as I think there should only be one Kiro instance or whatever that is called. My first task for today once I got back to working with Kiro.

🟠 VPC costs too much for this test project. $144 last month just for testing out deployment of VPC endpoints and IPAM. Does delete and re-deploy double my costs? And by the way I want VPC endpoints not application layer controls which do not provide the same security value. I already exclude NAT from this project though it is an option. I also tried Transit Gateway and was expensive.

🟡 Make sure VPC endpoints are optional and not configured eveywhere until confirm everything else is working properly to reduce costs excpet possibly the auth Lambda.

🟡 UI: Step completion prompt is inconsistent. Sometimes has Quit and Exit. 

🟡 Management Env Account List is incorrect in verification step. It's missing the security account and backup account. There are also too many accounts in the management environment. The script can be used to deploy the job framework, AMIs and other accounts to the environment as needed but for my purposes I don't need that. Remove those account.

🟡 Close account is not working and before closing an account need to fix the following: change alias name, change account name, change email address - to avoid conflicts if need to recreate the account.
