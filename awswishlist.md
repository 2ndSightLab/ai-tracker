
# My AWS Wishlist Items Related To This Project

## AWS Wish List

This is a list of my wishes on the [AWS Builder Center](https://builder.aws.com/wishlist) related to this project. These are things that cost me time, money, or both or didn't allow me to implement the security controls and cost management controls the way I wanted. I mean it doesn't hurt to ask, right? 

These wishes are likely most applicable to those involved in AWS account security, cost management, governance, and Kiro CLI users. If you like any of these wishes I included a link below and you can give them a thunbs up if you would like to see them implemented as well.

## Status

🟠 Open Wish related to this project 🟢 Resolved

## Wishes

🟠 I want to be able to select any model available in Amazon Bedrock in Kiro. https://builder.aws.com/wishlist/3EdZnhuYbi5bCR6vBvzE4THvE8C_w/i-wish-we-could-select-from-all-the-bedrock-models-in-kiro-cli-and-others

🟠 If I forget to change the email address, alias or name of a closed account I can't recreatea new one with the same information. https://builder.aws.com/wishlist/3ETtg4AwifUcBqGG03ZknTjF1g3_w/cannot-use-alias-email-name-that-was-used-on-a-closed-account

🟠  I'm having to redo my Kiro subscription again. I don't like it that overages cost more than the base plan. That means I keep having to delete and create subscriptions to get the lowest price per token at all times. Even though I deleted some subscriptions at the end of the month in the past they got renewed. The fine print says the rollover is UTC which I thought caused my initial issues. But then it rolled over pre-UTC at the end of the month and I still got billed for a subscription in the next month when I tried to cancel it because I as taking a trip. This whole monthly subscription thing is painful. Some months I need to use it a lot and others not so much. Pay as you go pricing like all the rest of AWS - one of the core principles on which the service was built - would be so much more cost-effective to manage. Monthly billing is simple - but in the end it is painful for the user and the customer when you get into the details of using it and are trying to track costs and get the best value. 

PLEASE VOTE FOR THIS WISH. You will save money if you are a heavy Kiro user and use over $200 per month and you won't have to keep switching plans and users to get the best price. You will only pay for what you use if you happen to not use the service as much in a particular month.

The other model I like is the Portswigger model where you can pay for a batch of tokens and use them as you need them. 

The current Kiro subscription model is a pain.

https://builder.aws.com/wishlist/3AKEJEKOukFAuKJYVme3zJQHVVF_w/pay-as-you-go-economical-kiro-cli-plan

🟠 VPC costs too much for this test project. $144 last month just for testing out deployment of VPC endpoints and IPAM. Does delete and re-deploy double my costs? And by the way I want VPC endpoints not application layer controls which do not provide the same security value. I already exclude NAT from this project though it is an option. I also tried Transit Gateway and was expensive.

🟠 When deploying delegated admins, all the CLI commands have different error messages. I would like to have consistent error messages with a number associated so I can handle them all with the same code. https://builder.aws.com/wishlist/3EIb2oBW7qkDj8E60yXZMct9Zmm_w/standard-error-messages-and-codes-please-defined-in-documentation-for-proper-error-handling

🟠 Had to delete my IPAM because I could not release an IP address in a closed account. https://builder.aws.com/wishlist/3ETscwuhjHF9Jy9CKxWYgUKFXUj_w/cannot-release-eip-in-closed-account-using-ipam
https://builder.aws.com/wishlist/3ETEXLx2zZ9GFzQHFYKqmJBcS9M_w/kiro-in-aws-console-shows-5-active-subscriptions-when-there-are-only-4-see-screenshots

🟠 It is complicated to allow the services allowed in an AWS account. I've had issues doing things because I've been blocked by SCPs unexpectedly as a result.https://builder.aws.com/wishlist/3ESxhi8NtKmwtEWuZGsOuLXy2Qo_w/easier-way-to-define-services-and-actions-allowed-in-an-account

🟠 Deleted an AWS Identity center user but the subscirption was still active. https://builder.aws.com/wishlist/3EPznRDZMYLT49pXhseetMjfBa3_w/i-deleted-an-aws-identity-center-user-but-the-kiro-subscription-plan-was-still-active-please-make-sure-subscription-gets-deleted-with-user

🟠 Got blocked because the same SCP for allowed regions does not have all global services in it. https://builder.aws.com/wishlist/3EPxyllN1bbH05lQOpAzbY0QfEG_w/update-service-control-policy-for-allowed-regions-in-documentation

🟠 Would love to have a global condition tag for global services so I don't to update the SPC when services change. https://builder.aws.com/wishlist/3EPyR5RzXZFnAmk73tsSqT4oQAa_w/new-method-allowing-global-services-in-region-specific-service-control-policy 

🟠 I want to be able to manage budgets for my accounts in a delegated admin account (my Accounting account). Because I don't want to take actions in my management account I'm currently managing budgets in every single account. I would like to be able to create a separate delegated budget admin for each environment so organization can delegate budgeting to the head of an LOB or department manager or product owner assigned to an environment (OU) https://builder.aws.com/wishlist/3ENCSBRPEeL3dKz9POY14EnZ4rJ_w/cost-management-delegated-administrator-in-aws-organizations

🟠 Could not log an issue with Kiro CLI custom agent not deployed in home directory using CLI (not TUI). Also it requires GitHub credentials and I do not give my agents GitHub credentials. https://builder.aws.com/wishlist/3EKpq8aeFC8FgkduqlJg5iioBWN_w/can-you-please-fix-kiro-cli-issue-not-working-with-custom-agent

🟠 Found it really confusing to delete an IPAM pool and IPAM https://builder.aws.com/wishlist/3E46zJ0uQmSowGKuw8FEUBmPa8D_w/very-confusing-to-delete-ipam

🟠 Crazy one that will probably never happen - shared ENIs https://builder.aws.com/wishlist/3CwU2CB8h5G3vPIiMqwh6WAKc6w_w/create-eni-with-proper-networking-and-share-with-ram

🟠 Can't see VPC Flow Logs for shared VPCs in the account to which they are shared. Would like the option to share them: https://builder.aws.com/wishlist/3CkNQ2tBuuFzGSZjuRPUNiENpWC_w/share-vpc-flow-logs-through-ram

🟠 When I share some things with RAM the name of the resource doesn't show up in the account to which it is shared. https://builder.aws.com/wishlist/3CkJD4qHgRT4gx3lcfzzXOb551N_w/ability-to-share-name-of-network-resources-when-sharing

🟠 Anthropic's model told me I could use a shared security group for may lambda functions after it had initially put them in what I thought was the wrong account. So I rearchitected my whole code base to move the to the network account. Then I tested it and no. They have to be in the same account as the lambda function. That is problematic for more reasons than one. I would like to create one security group and share it in some cases but I ended up just refactoring all the code to return it to it's original state. Why can't Lambdas use shared security groups: https://builder.aws.com/wishlist/3CkItsAbmt1Ejyunyk8E2H7NvSo_w/allow-lambda-to-use-ram-shared-security-groups

🟢 Kiro plan mode. Ugh no. THANK YOU. https://builder.aws.com/wishlist/3Bj8bjsMmuiRGwdXYKcr7n4SYiZ_w/kiro-cli-please-confirm-before-going-into-plan-mode-and-provide-shortcut-above-prompt-to-exit-plan-mode

🟠 Automatically end sessions when plan has ended: https://builder.aws.com/wishlist/3BSzYWdtlumRyuB4gSrPyzvY05V_w/automatically-log-me-out-and-terminate-all-sessions-when-kiro-plan-used-up

🟠 Incorrect IP in policy so cannot use IPAddress condition to restrict access to assume role in console with MFA. I get around this by creating a policy that uses the IPAddress for the action that it works with IPAddress but not MFA and MFA with the action that works with MFA but not IPAddress. https://builder.aws.com/wishlist/3BRoMdDzlCs5XBlhZEEEt7OzXMn_w/incorrect-ip-address-in-aws-assume-role-in-cloudtrail-cant-apply-source-ip-condition-in-policies

🟠 Prefix list for every service. I came up with a work around with the AWS JSON IP range list and created my own IP ranges. But the IP ranges in that document are not granular enough which is the other problem. https://builder.aws.com/wishlist/3AExvFQSsi84BV9PQeUm7hN8qV6_w/prefix-list-for-every-aws-service-region-and-all-aws-services-for-easier-network-management

🟠 Create a policy that says the principal can only delete or modify resources it created https://builder.aws.com/wishlist/3AExAgHvsMsIaSHBbSIjWyxjdY6_w/create-a-policy-that-says-the-principal-can-only-delete-or-modify-resources-it-created

🟠 The AWS Pricing API is incomplete making it pretty much useless. https://builder.aws.com/wishlist/3AEbZTUvVORoKr1RW4d2Twgl9Uw_w/add-all-services-and-features-of-services-to-the-aws-pricing-api

🟠 When you are using AWS IAM, CloudFormation, the AWS CLI, and various APIs the same thing has different names all over the place making it difficult to programmatically integrate with all of them. I started creating a mapping but it would be great if AWS had a name mapping API or something where you could look this up. Also the AWS CLI doesn't have a way to list all service names and all commands so I do a hokey work around. https://builder.aws.com/wishlist/3AEZjv9MemxNzRpd1bdX24EZUNv_w/service-name-alignment-or-mapping-different-sources-have-different-service-names

🟠 Kiro created invalid role for EC2 instance and IAM allowed it to be deployed - would like it to fail on deployment https://builder.aws.com/wishlist/3AEVYwSJWDAuoGTkz56Q7A2IY17_w/kiro-created-invalid-role-for-ec2-instance-and-iam-allowed-it-to-be-deployed-would-like-it-to-fail-on-deployment

🟠 This dispatch error on logout is really conffusing when you start out. It means your session has timed out. Shoudl say something better and have the option to exit, but the option to login behind the scenes and continue. https://builder.aws.com/wishlist/3ABqjssN0gfIBOJ7ON23pQ3YpZC_w/automatic-redirect-to-login-when-session-time-out-in-kiro-cli

🟠 Terminate a session completely instead of just blocking with a policy - IAM. This has always bugged me. The session remains active if you block it with a policy. If you remove the policy the session is still active. Need a way to actually terminate the session meaning it's GONE. https://builder.aws.com/wishlist/3AB8llUn6KGE8ZxXQTEUD8p2n7Y_w/terminate-a-session-completely-instead-of-just-blocking-with-a-policy-iam

🟠 Support or buildx and SBOMs when using Lambda containers https://builder.aws.com/wishlist/3AB7Rx65B0Iiyv5huuh9KDHu1rQ_w/support-or-buildx-and-sboms-when-using-lambda-containers

🟠 File name completion when using ! in Kiro CLI https://builder.aws.com/wishlist/39xuD45F9cv4mJnrMGTTYkqF7Wx_w/file-name-completion-when-using-in-kiro-cli

🟠 Kiro doesn't follow rules in README (or steering file or anything else) -- really this can't be fixed without some deterministic solution and probably really can't be fixed at all. When I rwote this it was more of wishful thinking. And it's not Kiro. It's all AI models. Kiro may be better at undoing what it did - somethings -- and again that's not Kiro that's the model I think. But I still have cases where it forgets what it just did.  https://builder.aws.com/wishlist/39xeZHPgs2YbY3fl3iHoYGFyh5K_w/kiro-cli-does-not-follow-rules-in-readme-and-then-it-cant-undo-what-it-did

🟠 The error message when you enter an incorrect region is confusing and I wish it would stop right at that point. https://builder.aws.com/wishlist/39urIqzZx3dLxhWQbk9yOpINdqe_w/if-i-enter-an-invalid-region-logging-into-kiro-cli-stop-me-there

🟠 Copy and paste in CloudShell on a Mac https://builder.aws.com/wishlist/39uqjcSSSL4xNycUAAbTJsKj6EC_w/copy-and-paste-in-cloudshell-on-a-mac

🟠 Termination protection for EIP in IPAM pool https://builder.aws.com/wishlist/39r3UNLWKBoXF14vnYnumh0Le2K_w/termination-protection-and-resource-policy-for-ipam-address-pool

🟠 I really dislike device code flow becuase it is constantly phished. I just want to use the mechanism I use to enforce MFA with an IAM role I've written about many times. There are examples in the aws-scripts repo in my profile if you don't know how to do that. https://builder.aws.com/wishlist/39pNDkwg1erGDg464JD9qCu8igH_w/ability-to-login-to-kiro-with-iam-user-and-no-device-code-flow

🟠 User name for Kiro needs to show up in CloudTrail https://builder.aws.com/wishlist/39pLm6X6TXbwgCqYIti039aTswx_w/need-to-see-username-associated-with-an-error-in-cloudtrail-for-kiro-sso-login-failures

🟠 Include a resource for every action in CloudTrail where appropriate so search works correctly. https://builder.aws.com/wishlist/39pLNVTBveWsdroWf22KV57R8yR_w/include-a-resource-for-every-action-in-cloudtrail-where-appropriate-so-search-works-correctly

🟠 Ability to Force MFA Yubikey Button Push EVERY TIME I Switch Roles in AWS Console. The keys to the kingdom AWS Identity Center role switching type access is risky. https://builder.aws.com/wishlist/39pL24LNZciQi8y8bv1DZoihrLk_w/ability-to-force-mfa-yubikey-button-push-every-time-i-switch-roles-in-aws-console

🟠 Show KMS keys with RAM and have them shoe up in select list when creating an EC2 instance (see screenshot) https://builder.aws.com/wishlist/397qZjAcvAexuRrrkirbOcF1TTr_w/share-key-with-ram-and-shows-up-in-ec2-select-list

🟠 AI troubleshooting for CloudTrail error. I saw something like this in the console but it needs to allow you to ask follow on questions. https://builder.aws.com/wishlist/397pnNiP3bmDWyxOqLHENWQY9WC_w/ai-troubleshooting-for-cloudtrail-error

🟠 Do not show accuont number in url when switching accounts. Account numbers are not supposed to be secret but I still do not want to share them unneccessarily in a URL. If in the request/response might be hidden but not in the URL. Unfortuately S3 buckets are also in URL sometimes and account specific buckets have this same issue. If it's in completely encyrpted data fine but as demonstrated in one of my blog posts this information is available to attackers sniffing traffic. They can associate a user IP address with a particular account which may have some usefulness in certain types of attacks (assoicating a particular user IP address with a particular account they may be targeting. https://builder.aws.com/wishlist/397rHL9DpejZJdDqkKTdmfsdYn4_w/do-not-show-the-aws-account-number-in-url-when-using-multi-session-feature

🟠 This has bugged me foreever. Why do I have to click three times to get to the place where I want to change the encryption key for an EC2 instance. It feels hidden rather than obvious and encouraged. https://builder.aws.com/wishlist/397ojhJjMxb17rDQLJC0EUWezj5_w/please-dont-make-me-click-three-times-to-get-to-encryption-key-for-storage-in-ec2-console

🟠 This is another crazy one. Create a key pair and share it in RAM so an admin can create the SSH key in an account where they can manage SSH keys and the user controls the starting, stopping, and logging into the instnace. https://builder.aws.com/wishlist/397oBuJhv55YX8gCmgaknlVlBhg_w/create-and-share-an-aws-ec2-keypair-associated-with-a-user-using-ram

🟠 Keep the network traffic for firmware updates on the AWS network. https://builder.aws.com/wishlist/397nXH0vjkAxBDv2gqbjqzrBn8T_w/keep-network-traffic-for-firmware-updates-on-the-aws-network

🟠 Let me choose what I see when I log into the EC2 service dashboard (or any dashboard for that matter) https://builder.aws.com/wishlist/397nBUcYDdMM7zFylwnp1vOvJME_w/let-me-choose-what-i-see-when-i-log-into-the-ec2-service-dashboard-or-any-dashboard-for-that-matter

🟠 Let me choose what screen I land on when I log into an AWS account https://builder.aws.com/wishlist/397mf1Mnn98uWQRxncGxbtETLSD_w/let-me-choose-what-screen-i-land-on-when-i-log-into-an-aws-account

🟠 Choose My IP when creating an AWS prefix list - show me my ip address and let me choose it for my remote access prefix list shared to every account so I can update all the remote access security groups in all accounts in one place. https://builder.aws.com/wishlist/392kUggY5rGI23ICt6WjZlLVT3I_w/choose-my-ip-when-creating-an-aws-prefix-list

🟠 Another crazy one. Allows administrator management of AWS access keys. Resource Policy on Developer Access Key with MFA and/or IP conditions. https://builder.aws.com/wishlist/392izAOoyL1ihFiDlS9adqIBis1_w/resource-policy-on-developer-access-key-with-mfa-andor-ip-conditions

🟠 Simplify Cross-Account Access by Using RAM for everything. I've been using RAM if you could use it more globally it would be easier to manage policies on resource and share them from global locations. I put all my KMS keys in my organization in a single account. I also have AMIs used by the whole OU in one account. I'd love to use RAM in the KMS account to share the KMS keys and RAM in the AMIs account to share the AMIs. https://builder.aws.com/wishlist/392iQglVJcELS3NGGRhArbhFjGO_w/simplify-cross-account-access-by-using-ram-for-everything

🟠 When I open the AWS console in us-east-2 I'm seeing traffic to regions all over the work including Asia, Europe, Mexico, Canada, and South Africa on top of other us-east-2 regiosn. Doesn't seem right. There are so many breaches involving sending data to alternate regions that I really do not want to see this. It haappens when I use other services as well. The traffic from my computer should remain in my selected regions and if needed traffic should stay within the AWS network to get to other regions. https://builder.aws.com/wishlist/392hfO1cY7ldkULrw12B2YgHPWw_w/please-keep-all-network-traffic-in-region

🟠 I waste time trying to launch instances when I don't have KMS configured correctly to give the user that I'm logged in as protected access. It gets all the way to launching the instance then fails. Make it fail when I try to select the key and tell me what needs to be fixed. https://builder.aws.com/wishlist/392euD9I2Wd3Y7Ua4VoyXP7rcti_w/if-i-do-not-have-permission-to-launch-an-ec2-instance-due-to-lack-of-kms-key-permissions-warn-me-before-i-launch-the-instance-and-tell-me-how-to-fix

🟠 CloudTrail filter on errors. Why does this not exist? It seems like the single most useful case for CloudTrail. Many times when you're going to CloudTrail aren't you trying to find errors? https://builder.aws.com/wishlist/392eMFoWYcyIU6zaAZNIKpBZQIL_w/cloudtrail-filter-on-errors

🟠 CloudTrail error column setting - on by default. Why are they not? Isn't one of the most common use cases in CloudTrail looking for what caused an error? https://builder.aws.com/wishlist/392dYfiCpiV12TSZbDHYiTAcpQJ_w/cloudtrail-error-column-setting-on-by-default

## Not reported

🟠 This is just weird - I programmatically created a kiro instance to configure a new account. The instance is there but no sesttings are onfigured. When I enable Kiro it asks for an email. I'm logged in with an IAM user and I'm using a standalone identity center. I've programmaticaly created my new user which in theory has no permissions. So which email? I use the email address of the admin and it doesn't work because it is an IAM user. I use the email of the identity center user and it is accepted and enables Kiro even though that user has been granted no permissions. In that case why not just enable by deafult automaticaly because it is the same difference.

🟠 Can't change the url assocaiated with kiro account in console only the name after the above scenario occurred. That may be by design but I used to be able to rename it. But I do understand the security implications.

🟠 Why does the console still say Q developer in the service list?

🟠 I think the AI model is understandably getting confused due to the way IPAM works. I would have had the EIP allocated in the IPAM itself and then share that out with RAM share to the acount that needs to use it. That way if the account is deleted (one of my other issues) the EIP can still be managed by the IPAM account. This is all confusing because my bootstrap script has to switch roles from the IPAM account to the account using an IP Pool to create a new EIP. The model just can't figure that out without guidance. I suppose this is because a network team might want to allow end users in the accounts add and release IPs as needed. But it's confusing for the model and difficult to maanage when the account using the EIP gets deleted. 

🟠 I want to be able to define what appears on the default dashboard when I create a new account. I never use the application thing and I don't wnat all those lists appearing in evry account. I just wnat the cost, the recently visited, and if it's a service specific account I want to define which service dashbard I see on the main page like KMS or whatever. But if it's a KMS only acocunt really I just wnat to land directly on the KMS page. If i use two services in an account like KMS, ACM then I woudl want both those on the home page only. All that stuff is making extraneous network connections (somtimes to wrong region) and cluttering the logs.

🟠 Kiro or model keeps saying changes were cancelled and not written when I hit ctrl-c and tell it to stop and restore what it just did - when they actually were written. It should check before saying that.

🟠 When I close an account I can't reuse the email, name, and alias in a new account. I also found out that buckets using the naming convention locked to a specific acocunt also can't be reused. Should warn users of that prior to closing account and have some kind of override for that or auto nenaming feature so can close and create new accounts with same info but still be able to restore the old ones if needed.

🟠 Let me turn off telementry everywhere including AWS console. Seeing too many repeated connections that beacon like a C2 channel. Just want to turn it off. 

🟠 I just had major issues with Kiro teleemtry...what is that all about? Need a better breakdown for monitoring purposes that shows exactly what part of the infrasatructure is causing deleys - is it the model? Is it telemetry? Is it Kiro infrastructure? I only had this issue with a custom agent while the default agent showed no such degredation. Why? Would like more visibility into all of that to pinpoint issues and know how or what is actually causing the problem. Once I turned off telementry the model behavior improved as well. I don't know if that was a coincidence as Antrhopic changed is suppoed rules for AI resaearch at the same time. I don't know if my research got caught up in that but I'm just trying to deploy AWS infrastructure so that wouldn't really make sense.   

🟢 🧡 Note related to the last post. I had some issues with slowness around midnight with Kiro and memory-related exceptions which seem to have been resolved. 

🟠 Let me turn off os notifications in the AWS console. Seeing too many repeated connections that beacon like a C2 channel. Just want to turn it off in some accounts and maybe it's only on in the acount where I actually want to see notifications. Let me use that with AWS Organizations and see all the notifications for my organizations in one account. Let me send a notification to my cell phone if a service I am actively using goes down rather than these constant pings and traffic in accounts. 

🟠 Let me turn off os panorama requests in the AWS console. Seeing too many repeated connections that beacon like a C2 channel. Just want to turn it off. I find panorama API calls odd because Google aimode reports Panarama as a deperecated client camera service. What even is that?

🟠 I don't know if or how you can fix it but would really like AI agents to stop making these mistakes:

https://github.com/2ndSightLab/ai-tracker/blob/main/mistake-tracker.md

🟠 I see the new VPC see all regiongs thing in the console and that's interesting. But the problem is that it's reaching out to eveyr domain and IP in every other AWS region and I block those. If I'm in the console in let's say us-west-1 then I only want to allow traffic to us-wast-1 and us-east-1 (because I must) and not every other region all over the world. So that function doesn't work. Having it go straight to the region has some use cases but what I would prefer, unless I explicitily allow  multi-region traffic for testing purposes, is to have that traffic go through my current region to the AWS network and then from there internally to other regions. That prevents some sort of MITM interception on the Internet. The whole offloading of traffic to that other region is nifty but is less secure. A lot of data breaches involve moving data to other regions or access via regions customers are not paying attention to. That's why I have an SCP in my account to lock down actions to specific regions. However, that SCP does not apply in the AWS console wehre it is a free-for-all. I see traffic to endpoints all over the world. Let me lock that down so if I see something going somewhre else I can instantantly know something is wrong.

🟠 I also do not like the "global" endpoints that capture data from everhwere and I can't tell what region they are in. That hs the same problem as the last bullet point. That traffic could be going anywhere given the vague nature of the JSON IP ranges - which I would like to be more region specific and granular to the detail of which services are being accessed instead of everything just being "EC2". Make each connection region specific so I can see where my traffic is going. Allow me to open up to more regions for better performance or select different regions if something is down. Maybe this is an advanced feature for customrs that want more control over their traffic in the AWS console. And maybe there's an alert if for performance reasons customers should switch to or allow a different region. For more information on why more granual endpoints are better see the security report on Microsoft Blizzard wehre enterprise and consumer endpoints were blended and sent to the same endpoint and therefore higher secruity and lower security traffic were mixed. If they had segregated those endpoints entterprise customers would not have been affected. In thsi case, and because I do not have an enterprise account, I would prefer regional segregation. I want to know that my traffic is not being sent to Europe, Africa, Asia, or Latin America and if possible, keep it in my own region. This is important not only for security but to maintain traffic within the bounds of the US where US laws are applicable.

🟠 What is "panorama"??? I keep seing that domain and when I look it up it says it's a canceled AWS camera service? Can you please give that an appropriate DNS name and provide documentation so I know what that is doing?

🟠 What is the .ai domain. No AI automagic stuff in my AWS console please.

🟠 I would prefer no third party domains when I load the AWS console. I see Adobe and Demdex. Can't you front those with your own doamins so you can see the traffic going to those third party domains? Or if you do inspect that traffic can you document and explain what those are used for and why they exist?

🟠 What is tangerine box? Please provide more information about each domain and its purpose and why it is needed. Can I turn this off? It's another thing that seems to be constantly showing. Too much random traffic.

🟠 When I go to the console in a us region why am I seeing EU regions popping up and Asian regions? I shoudl be getting the nearest regional endpoint or at least only US regions??? Maybe if an out of country region is required for perfromance region you ask the customer if they want to allow that - and in my case I do not.

🟠 I know this is not directly AWS but can you get glm-5 model to stop launching a continaer with root privileges? At least that container appeared when I used that model through Kiro. I presume it was that model because it appeared after I used the model for like 5 minutes and it was too slow to be useful. I shut it down but the container persisted. Kiro CLI on Amazon Linux.

🟠 Kiro or model keeps adding wory token wasting comemtns to files. All my requiremstns are in readme. I have a eruqiremnt to add a single lien to each file referencing the readme. Kiro or the model keep breaking that rule repeatedly wasting my tokens in the first place to write it and in the second place multiple times to fix it. Please make that stop.

🟠 Would like simply to have a --no-banner flag for no banner in no-interactive mode.

🟠 Having problems getting my agents to work correclty unless I use --classic mode. Why. What changed in newer versions that broke that? I am afraid to update Kiro now. I need to look into this more but I'm not able to get no-agent mode working correctly unless I'm in classic mode so far. Also my entire agent frameowrk doesn't work with the TUI.

🟠 Why am I seeing repeated connections to the IAM api after I'm already logged in on main AWS page? Why do I see multiple attempts to connect to a help domain? I'm not doing anything just sitting here looking at the screen? I blocked them and it still seems to work. Would like that to not happen.

🟠 When I visit the Kiro page in the AWS console I'm seeing sso connection attempts all over the world. Why? Please keep that in my own selected region only. It's connecting to Europe, Asia and others via sso domains.

🟠 There is a reason - and I'm trying to remember what it is here - why I cannot create an SCP to deny all external access using the OU path conidtion. It doesn't work for all types of resources, though I can't remember which ones right now. But it would be easy for someone at AWS to test this. Add an OU SCP that denies any actions except those perfomred by acounts in the OU. Test all AWS actions to see which ones are valid but get rejected. I would like that to work so I don't have to individually add each acount that is in the environment in my policy.

🟠 It is difficult to create a read only and delete only scp to allow read and delete actions only for any unauthorized regions. I want to grant an addmin or drrift detection tool read only and delete only actions in any unauthorized regions to find and remove unauthorized resources. the problem right now is that I cannot use a construct like this to allow all describe and delete actions in my policy:
```
allow...

*:delete-*
*:describe-*
```
I have to list every single service like this:
```
ec2:delete-*
s3:delete-*
iam:delete-*
ec2:describe-*
s3:describe-*
s3:list-*
```
So as you can see there is no easy way for me to add an allow drift detection and clean up VPC to easily detect and remove rogue resources without also allowing adding new resources.

🟠 Create aliases so all services have the same action set instead of one off differently named acctions. Some services use list and some use describe and some use delete, detach, or different verbs for the same actions. You do not need to change the existing actions just create an alias so that every AWS CLI resource has a consistent action accross all services. Then make it easy to create an SCP to only allow the consistent aliased actions so all services can have the allowed same actions in all cases and not have to handle all the one-offs and variations.

🟠 Ability to use a Prefix List in an AWS IAM or resource condition in a policy. Why? I set my admin IP in a prefix. When that IP changes every policy would automatically use the new IP.

🟠 I used the option to diagnose an error with an IAM policy in the AWS console and it's connecting to EU-central region when I am in a us-east region. That should stay within my selected region or ask me first if it needs to connect to some other region.

🟠 When I add a new user in AWS IAM Identity Center (standalone) and then I log into that uesr's email and click the verify the link, the AWS SSO console does not show accurate information about that user until I completely leave the service dahsboard and come back. Clicking to another menu does not help and no way to refresh the page. Can be confusing for people new to the srvice and slightly annoying to those who know what's going on. :)

🟠 Save another way is actually more secure than using a PassKey as it saves the data to the Yubikey. Instead of save another way it should be "Store key to laptop" or "Store key to Yubikey (recommended)". I know this probably doesn't align with some standard but I think the standard is flawed. Saving to Yubikey is more secure because you can remove the Yubikey when not in use and not subjecct to attacks on a much more complicated OS.

🟠 When adding MFA in AWS Identity Center (standalone) for use with Kiro, it does not make me enter the Yubikey pin when I choose save another way (it should).

🟠 On logout trying to connect to EU panorama domain. Why? No, please. Also marketing domain. Prefer did not do that.

🟠 When I create a new account the reuqest succeseeds but in the AWS Organizations console I see no indication of that on any screen I look at. I can go to CloudTrail and see that the request succeeded. I have to completely refresh the AWS Organizations page to see the account. It's confusing. 

🟠 AWS Organizations has way too many different kinds of policies. There are SCPs (Rules that apply across the board in an organization to AWS actions), Resource Policies (Policies that shoudl work the same way for every resource but currently do not to define who is allowed to access or take actions on or with a resource), Principal Policies (what a user or application can do), Trust Policies (who can assume a role), and RAM Sharing Policies (to see everything shared across an org in one place). Consolidate please. Why are there so many one-off separate policies? Make Organization settigns just settings for all the weird one off things.

🟠 Make the captcha easier to read. It's supposed to stop bots but it's so hard to read I never get it right on the first try. Or something else is going on. Is anyone getting it right on the first try?

🟠 I cannot add MFA to an admin on an account in an organization in the new user setup flow. I have to skip it and do it in the AWS console. Is there some weird network traffic in that new user network flow that is using a global or out of region domain that is not used in the AWS console?

🟠 Logging into a new account in a new organization in a brand new AWS account and I am getting popups for STS in aws regions all over the place not in my selected region. Please restrict that to my seleted retion. I have removed all the widgets except cost but they still keep coming. And SCP for this account only allows us-east-1.

<img width="566" height="575" alt="traffic" src="https://github.com/user-attachments/assets/eeafc136-cb9e-4a98-9e36-58ca760d8309" />

🟠 Trying to use Amazon Q in console to create an SCP that allows creating a standaloen identity center instance and kiro and 1.) it gave me an SCP that doesn't work. 2.) It's too slow 3.) can't stop it once it starts thinking and thne it takes forever before I can correct what I wanted to ask. It's so slow right now I just shut it down.

🟠 Trying to toubleshoot an SCP looking at countrail to figure out why it's blocking creation of stand alone identity center and nearly impossible to figure out. I can't filger on error messaes. The error messages are cryptic. I can't find the error mressages that are related to that specific action getting blocked. There's to omuch noise in the logs. There are too many other random failures for other services like health and cost and such. There's a dry run exception for Amazon Q. I try refreshing and performing the action again and still can't pinpoint the issue. Not all events have resource type / service in them.  Here's what I would expect: Go to to CLoudTrail. Filter on errors read only or not. Filter on Identity Cetner. Pinpoint the problem. The only error I get in the console is: 

You need permissions
You do not have the permission required to perform this operation. Ask your administrator to add permissions.
You don't have permissions to access this resource.

Digging through the logs I find this which is not very helpful - my user has full SSO permissions, is the root user for the account.

```
    "eventSource": "sso.amazonaws.com",
    "eventName": "DescribeRegisteredRegions",
   "errorCode": "AccessDenied",
    "errorMessage": "An unknown error occurred",
``` 
Finally Q pops up somehow and I get this
```
The denied access is caused by an SCP (Service Control Policy) that explicitly denies to perform ``iam:CreateServiceLinkedRole``. Consult your administrator before performing the suggested steps to resolve the error. They should check your SCP in the AWS Organizations for a `"Deny"` statement for the action ``iam:CreateServiceLinkedRole``, which is often used intentionally.

1. Sign in to the AWS Organizations console. You must sign in as an IAM user, assume an IAM role, or sign in as the root user (not recommended) in the organization's management account.
2. On the **Service control policies** page, choose the name of the policy that you want to update.
3. On the policy's detail page, choose **Edit policy**.
4. Edit the policy to remove the `"Deny"` statement for the action ``iam:CreateServiceLinkedRole``.
5. Review the updated policy for correctness, and then choose **Save changes** to save your changes.

```
A few problems with this. ServiceLinkedRole? Those are not subject to SCPs so prefer not to use them. Also, I have an SCP allowing that according to instructions I was given by Q. >>>  I cannot find this failure in the logs???
And worst of all > a free for all policy to create any service linked role instead of only the one(s) taht are needed in region needed by specific IP address (mine, not yours), and MFA required.

The only error I find for ServiceLinkedRole is:
```
  "userAgent": "organizations.amazonaws.com",
    "errorCode": "InvalidInputException",
    "errorMessage": "Service role name AWSServiceRoleForOrganizations has been taken in this account, please try a different suffix.",
    "requestParameters": {
        "aWSServiceName": "organizations.amazonaws.com",
        "description": "Service-linked role used by AWS Organizations to enable integration of other AWS services with Organizations."
    },
```
Oh and then randomly I put a restriction on my SCP to only allow actions in region us-east-1. I hit the enable button wone more time. And it works. What? Is this just a timing issue? What is going on here it is very, very confusing.

Oh and I forgot to mention I removed the permission to CreateServiceLinkedRole from the SCP before that also. So telling me I need to allow creation of a ServiceLinkedRole in the SCP which both Amazon Q and Google aimode was telling me to do was not the problem.

Aha I also had turned off all firewall rules so perhaps something was connecting outside of the selected AWS region (us-east-1). In addition, when I went back to enable my firewall rules it said it had blocked all traffic. I did not create that rule. I am constantly having problems with Little Snitch enabling all or disalbling all rules and trying to figure that out.

🟠 AWS console when I try to add KMS key to identity center tells me that I do not have permissions to list aliases but when I go to CloudTrail I cannot find the failed action and error related to that attempt.

🟠 When diagnosing someeting with Amazon Q need to be able to ask follow on questions when it gives incorrect or incomplete answer.

🟠 My network allows access to regions outside of the one I'm working in and strange connections to undocumented domains. I don't know if that is waht is causing this but Identity Center console looks wrong in two different AWS accounts in two different organizations as a result

<img width="866" height="447" alt="idc2" src="https://github.com/user-attachments/assets/a1d91996-1b26-404e-ad01-bde2b7f3e9b4" />

🟠 Cannot remember if I wrote this already but Kiro console also tries to connect to AWS SSO regions all over the world rather than my selected region. Still says Q in the unified search dropdown and still seeing traffic to q and code whisperer domains.

🟠 Please quantum encryption for Kiro CLI connections. I'm seeing a connection to keep the socket open and one to send the requests (right)? But not quantum?

+    15: Port/service: TCP 443, HTTPS.
+    16: Application protocol: HTTP/2 (ALPN negotiated h2).
+    17: TLS version: TLS 1.3 on every endpoint.
+    18: Cipher suite: TLS_AES_128_GCM_SHA256 (AES-128-GCM AEAD, SHA-256).
+    19: Key exchange: X25519 ECDHE, 253-bit ephemeral (forward secrecy).
+    20: Cert signature: rsa_pss_rsae_sha256. Chain verification: OK.
+    21: 
+    22: Certificate (identical on all four):
+    23:   subject CN=codewhisperer.us-east-1.amazonaws.com
+    24:   SAN DNS:codewhisperer.us-east-1.amazonaws.com
+    25:   issuer C=US, O=Amazon, CN=Amazon RSA 2048 M04
+    26:   notBefore Feb 17 2026, notAfter Mar 18 2027



