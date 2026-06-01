
🟠 Open Wish related to this project 🟢 Resolved

6/1/2026

🟠 If I forget to chagne the email address, alias or name of a closed account I can't recreatea new one with the same information. AWS Wishist: https://builder.aws.com/wishlist/3ETtg4AwifUcBqGG03ZknTjF1g3_w/cannot-use-alias-email-name-that-was-used-on-a-closed-account

🟠  I'm having to redo my Kiro subscription again. I don't like it that overages cost more than the base plan. That means I keep having to delete and create subscriptions. Even though I deleted some subscriptions at the end of the month in teh past they got renewed. The fine print says the rollover is UTC which I thought caused my initial issues. But then it rolled over pre-UTC and I still got billed for a subscription in the next month when I tried to cancel it because I as taking a trip. This whole monthly subscription thing is painful. Some months I need to use it a lot and others not so much. Pay as you go pricing like all the rest of AWS - one of the core principles on which the service was built - would be so much better in my opinion. As of now I have to go in and figure out how to get a new user and subscription set up. The last time I tried to create a new user in a stand alone IDC instance in my AWS account the user jsut sat in pending and I couldn't actually login so I deleeted the whole instance and the whole account. Now I am trying to use my script to redeploy all that but my script broke with all my rejiggering so I'm in this catch-22 state where I have to manually create the IDC and user and Kiro instance if I want to use AI to fix my code and redeploy the Kiro instance and IDC in an automated fashion. The other problem I had was that when I looked at what got deployed by the AI generated code there were weird names and multiple instances or something in my Kiro setup. I need to go back and read the documentation and test out the code in a separate account maybe to figure out what is wrong with what it is deploying as I think there should only be one Kiro instance or whatever that is called. My first task for today once I got back to working with Kiro.

🟠 VPC costs too much for this test project. $144 last month just for testing out deployment of VPC endpoints and IPAM. Does delete and re-deploy double my costs? And by the way I want VPC endpoints not application layer controls which do not provide the same security value. I already exclude NAT from this project though it is an option. I also tried Transit Gateway and was expensive.

🟠 When deploying delegated admins, all the CLI commands have different error messages. I would like to have consistent error messages with a number associated so I can handle them all with the same code. AWS Wishlist: https://builder.aws.com/wishlist/3EIb2oBW7qkDj8E60yXZMct9Zmm_w/standard-error-messages-and-codes-please-defined-in-documentation-for-proper-error-handling

🟠 Had to delete my IPAM because I could not release an IP address in a closed account. AWS Wishlist: https://builder.aws.com/wishlist/3ETscwuhjHF9Jy9CKxWYgUKFXUj_w/cannot-release-eip-in-closed-account-using-ipam

🟠 Kiro shows incorrect number of active subscriptions. AWS wishlst: https://builder.aws.com/wishlist/3ETEXLx2zZ9GFzQHFYKqmJBcS9M_w/kiro-in-aws-console-shows-5-active-subscriptions-when-there-are-only-4-see-screenshots

🟠 It is complicated to allow the services allowed in an AWS account. I've had issues doing things because I've been blocked by SCPs unexpectedly as a result. AWS Wishlist: https://builder.aws.com/wishlist/3ESxhi8NtKmwtEWuZGsOuLXy2Qo_w/easier-way-to-define-services-and-actions-allowed-in-an-account

🟠 Deleted an AWS Identity center user but the subscirption was still active. AWS Wishlist: https://builder.aws.com/wishlist/3EPznRDZMYLT49pXhseetMjfBa3_w/i-deleted-an-aws-identity-center-user-but-the-kiro-subscription-plan-was-still-active-please-make-sure-subscription-gets-deleted-with-user

🟠 Got blocked because the same SCP for allowed regions does not have all global services in it. AWS Wishlist: https://builder.aws.com/wishlist/3EPxyllN1bbH05lQOpAzbY0QfEG_w/update-service-control-policy-for-allowed-regions-in-documentation

🟠 Would love to have a global condition tag for global services so I don't to update the SPC when services change. AWS Wishlist: https://builder.aws.com/wishlist/3EPyR5RzXZFnAmk73tsSqT4oQAa_w/new-method-allowing-global-services-in-region-specific-service-control-policy and 
