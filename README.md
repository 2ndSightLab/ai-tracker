# AI Tracker

## Objective

Track how long it takes and how much it costs to create projects with AI 🤖 in an attempt to optimize progress.

## Support this research

If you want to support of follow this research consider becoming a paid subscriber on my substack [technology and security research blog](https://teriradichel.substack.com). Paid subscribers can add comments and see the archives. Founding members can ask questions (i.e. consulting or training). You can also just sign up for free - no worries! All are welcome and appreciated. 🩵

https://teriradichel.substack.com

## Project Objective: AWS Bootstrap Script for AI Agent Environment 

Build a script to deploy, delete, and test an AWS environment to securely run AI agents. This includes my organizational framework and security controls to segregate environments and monitor AWS activity. Specifically I want to segregate my security testing, development, production, and management environments. The framework also sets up my organization with monitoring including budgets and security services used by delegated administrators (Guard Duty, etc.)

The whole point of this is to be able to quickly spin up and tear down environments for projects. As for agents I want to be able to quickly deploy new ideas. That is in part achieved by my job framework which is the follow-on project to this one, but I need first and foremost to have the secure base infrastructure in which to deploy my agent framework and agent resources. I also spin up separate environments for each penetration test so one test cannot affect another. If I am running AI agents in an environment and they mess it up, I can tear down the whole environment and rebuild it easily. In addition, it ensures that my agents cannot affect production resources with proper security boundaries. When something is deployed incorrectly or I have a billing issue I cannot fix, I can tear down the environment to stop the building and build a new one.

A full series on what I am developing in this project can be found here:

https://teriradichel.substack.com/p/toc-aws-organizations-and-ai-agent

More granular updates on X @teriradichel and the AWS Builder Center.

https://builder.aws.com/profile?tab=articles

## Tools and models

I'm primarily using Kiro CLI and anthropic models, though I do use Google aimode to ask questions at times and may branch out to test other models and technologies after this infrastructure is up and running.

## Issues:

https://github.com/2ndSightLab/ai-tracker/blob/main/issues.md

## Fixed:

https://github.com/2ndSightLab/ai-tracker/blob/main/fixed.md

## AWS Wishlist

https://github.com/2ndSightLab/ai-tracker/blob/main/awswishlist.md

## Time

I started this project around March 7th. I had to take a break for about three weeks in May. I haven't really worked on anything else besides this and blog posts because I keep thinking it is "almost done." I've also been working kind of long hours to do it and figure things out.

My initial post on this project tracks the start project and initial progress in 2.5 weeks

https://teriradichel.substack.com/p/what-ive-vibe-coded-in-25-weeks

The time it takes is demonstrated by feature completion and the timestamps in this GitHub repo, though my time may be taken away for other things periodically. 

## Cost: ##

### Costs while building an AI Agent Bootstrap Script and Framework
**Date Range:** Mar 7, 2026 - Jun 2, 2026

| Cost Category | Total | Mar 2026 | Apr 2026 | May 2026 | Jun 2026* |
| :--- | ---: | ---: | ---: | ---: | ---: |
| **TOTAL COSTS** | **\$1,389.34** | **\$359.07** | **\$387.55** | **\$621.52** | **\$21.20** |
| Kiro | \$613.43 | \$193.55 | \$129.07 | \$285.79 | \$5.02 |

Costs broken down by service can be found here:

https://github.com/2ndSightLab/ai-tracker/blob/main/cost.md

This data is pulled from a custom Dashboard I created in the AWS Cost Management serivce in the AWS Console. I copy and paste the data into Google aimode, translate it to markdown, and paste it here periodically. Note that the organizational costs include monitoring for a few other accounts that contain static websites, storage and where I do some security research and pentesting. Those account costs are not included but the cost of the organizational services includes those other accounts. I didn't bother to try to filter that out due to lack of time and I'm not sure how to do that wihtout looking into it further. The cost is minimal and not worth the effort at them moment. Also note there was a billing snafu in the month of May for which I did not get credit. There were $200 of tokens I could not use at all in that month. I had to go help a hurt family member and shut down the plan before I left but somehow when I got back it was still active and I got billd for another month. I had a knee-jerk reaction when I saw it and shut it down right away to stop the billing. I still got billed for it even though I didn't use it at all. So don't do that.

## Objectives

### Bootstrap Role ###

Role, policy and permission boundary deployed in root management account in AWS CloudShell.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Role | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| Policy | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| Permission Boundary | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 |
| Trust policy with MFA and IP condition  | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |

### AWS CLI Auth ###

Separate reusable project that handles configuring role profiles and role assumption with MFA.

I used some previously written code as a starting point in which the [role trust policies contain MFA and IPAddress conditions to assume the role and the user associated with the keys cannot do anything except asusme a role with MFA](https://github.com/2ndSightLab/aws-scripts/tree/main/scripts).

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Configure Role Profile | 🟢 | 🟢 | 🟢 |
| Assume Role With MFA | 🟢 | 🟢 | 🟢 |

### UI ##

Separate reusable project that handles configuring role profiles and role assumption with MFA.

| Feature | Deploy | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | 
| Reusaable Numbered Menu with Filter by letters | N/A | 🟢 | 🟢 | 🔴 | 🔴 |
| Reusable y/n/e prompt | N/A |  🟢 | 🟢 | 🔴 | 🔴 |
| Step completion prompt | N/A | 🟢 | 🟢 | 🔴 | 🔴 |

### Base Environment Resources ###

Resources installed in every environment. Some are optinoal.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Environment (OU) | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Accounts: IAM, KMS, Backup (in backup OU) | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Move accounts to OU | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Account aliases | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Admin users | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin user policy | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin roles | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin role policy | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Deployment Lambdas | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| S3 Logs bucket | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Logs KMS key | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: kms-account-allowed-services [env] | 🟢 | 🟢 | 🟢  | 🔴 | 🔴 | 🔴 |
| SCP: deny-external-access [env] | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: always-denied-actions [env] | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: env-allowed-regions [env]  | 🟡 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |

### Management Environment ###

The management environment contains accounts where my organization deletegated administrators exist.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Organization | 🟢 | 🔴 | 🟢 | 🟢  | 🔴 | 🔴 |
| Enable Org all features | 🟢 | 🔴 | 🟢 | 🟢  | 🔴 | 🔴 |
| Accounts: IAM, IPAM, Accounting, Org, Security, KMS, Security, Backup (in backup OU) | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Org resource policy | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate IPAM admin | 🟢 | 🔴 | 🟢 | 🟢  | 🔴 | 🔴 |
| Delegate Security Hub admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate GuardDuty admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate CloudTrail admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate AWS Config admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Firewall Manager admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Macie admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Inspector admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate IAM Access Analyzer admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Audit Manager admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Health admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Detective admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Backup admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Network Manager admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate VPC Reachability Analyzer admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Cost Optimization Hub admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Compute Optimizer admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| IPAM | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Root SCPs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| AWS Prefix Lists | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Configure GuardDuty | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Security Hub | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure CloudTrail | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure AWS Config | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Macie | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Inspector | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure IAM Access Analyzer | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Deny-All OU | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: always-denied-actions [root] | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: deny-leave-organization[root]  | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| SCP: always-default-org-root [root] | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: deploy-scp-require-imdsv2.sh [root] | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Environment SCPs | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: deny-all [account or OU] | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 
| SCP: org-allowed-regions [root]  | 🟡 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| Configure Security Alerts | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

🟡 Broke: Restructing scps - where are they deployed and fix naming conventio)

### Domains Envirnoment ( Base Environment +) ###

Domain name management. One for prod and one for test in my case. 
Can lock when not in use with deny all SCP.

| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: dns, backup | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Move Domain | 🟢 | 🟢 | 🔴 | 🔴 | 
| Move Hosted Zone | 🟢 | 🔴 | 🔴 | 🔴 | 
| Register domain | 🔴 | 🔴 | 🔴 | 🔴 | 
| Update Parent Hosted Zone (specific steps TBD) | 🔴 | 🔴 | 🔴 | 🔴 | 

# Work Environment Resources ( Base Environment +) ###

Environment where people log into EC2 instances.

| Accounts: work, backup | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| IPAM pool | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| IPAM EIP allocation | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Environment SCPs | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| S3 buckets (no KMS) | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS keys | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS policies | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS key aliases | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| VPC Flow Logs Role | 🟢 | 🔴 | 🟢| 🔴 | 🔴 | 🔴 |
| Remote Access Prefix List | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Remote Access (Work) VPC | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Remote Access Subnet | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Remote Access Security Group | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Remote Access Internet Gateway | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Remote Access Route Table | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Remote Access NACLs | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Remote Access VPC Ram Shares | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Remote Access VPC Flowlogs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delete default VPCs | n/a | n/a | 🟢 | 🟢 | 🔴 | 🔴 |
| Deploy Deployment Lambdas | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| S3 buckets (with KMS) | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Bucket policies | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| SSH Security Group | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| RDP Security Group | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| HTTP/HTTPS Security Group | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Budgets | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu Instance Role | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu ENI | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu Instance | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu AMI | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Amazon Linux Instance Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Amaxon Linux ENI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Amazon Linux Instance | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Amazon Linux AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Web Environment ( Base Environment +) ###

This is a separate project that allows deploying a static website in any web account in any enviroment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: web, backup | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deploy Web Lambda | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Test Environment (Work Environment +) ###

Some enviroments may include penetration testing and security research resources.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: project | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Burp ENI | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Burp Instance Role | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Burp Instance | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Burp AMI | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab ENI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab Instance Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab Instance | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

( And other stuff not shown here :^) 

### Kiro management environment ###

Separaete environment because it reuqires us-east-1. Manage Kiro subscriptions.
Also separates account from specific projects or activities.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Kiro | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Standalone Identity Center | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |

### Job + AI Agents Environment (Work Environment +) ###

The job framework infrastructure allows me to quickly and securely run jobs. 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: jobs | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Job VPC | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Subnet | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Security Group | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Internet Gateway | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Route Table | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Security Group | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job VPC Endpoints | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job RAM Share | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job VPC Flow Logs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Subnet | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Security Group | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Route Table | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Lambda Security Groups | 🟢  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth VPC Endpoints | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC Endpoint SGs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC RAM share | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC Flowlogs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| S3 buckets (no KMS) | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS keys | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Git Credentials Secrets | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Dev Instance Role | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Dev ENI | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Dev EC2 Instance | 🟢 | 🔴 | 🟢  | 🔴 | 🔴 | 🔴 |
| Job Dev AMI | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Route 53 Hosted Zone | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job/Auth Lambdas | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Lambda VPC Config | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| ACM Certificate | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| API Gateway | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| API Gateway CNAME | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| DynamoDB | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Backup Infrastructure ###

Back up infrastructure segregated from other infrastructure

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Backup OU | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Account Per Environment | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Archive Account Lambda Role | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Archive Account Lambda | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Archive Account Lambda SG | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Backup VPC | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Subnet | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Security Group | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Route Table | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Lambda Security Groups | 🟢  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Backup VPC Endpoints | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup VPC Endpoint SGs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup VPC RAM share | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Bacup VPC Flowlogs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |

### Run Menu Steps ###

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: |
| Share all amis to all acounts in ou | 🔴 | 🔴 | 🔴 | 🔴 | 
| IAM Acccess Analyzer Report | 🔴 | 🔴 | 🔴 | 🔴 |
| Prowler Report | 🔴 | 🔴 | 🔴 | 🔴 | 
| Enable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 | 
| Disable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 |
| Archive Account | 🔴 | 🔴 | 🔴 | 🔴 | 
| Move website | 🔴 | 🔴 | 🔴 | 🔴 |
| Transfer GitHub repo to Code Commit | 🔴 | 🔴 | 🔴 | 🔴 | 
| Transfer one Code Commit repo to Another | 🔴 | 🔴 | 🔴 | 🔴 | 
| Lock (apply deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Unlock (remove deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Deploy External AMI Share Key | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Share AMI To External| 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Deploy to single account (account in a different organization or standalone) ##

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Network | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| User | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Jobs Instance | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

