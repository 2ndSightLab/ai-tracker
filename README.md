# AI Tracker

## Objective

Track how long it takes and how much it costs to create projects with AI 🤖 in an attempt to optimize progress.

## Support this research

If you want to support of follow this research consider becoming a paid subscriber on my substack blog. Paid subscribers can add comments and see the archives. Founding members can ask questions (i.e. consulting or training). You can also just sign up for free - no worries! All are welcome and appreciated. 🩵

https://teriradichel.substack.com

## Project Objective: AWS Bootstrap Script for AI Agent Environment 

Build a script to deploy, delete, and test an AWS environment to securely run AI agents. This includes my organizational framework and security controls to segregate environemnts and monitor AWS activity. Specifically I want to segregate my security testing, development, production, and management environments. The framework also sets up my organization with monitoring including budgets and security services used by delegated administrators (Guard Duty, etc.)

The whole point of this is to be able to quickly spin up and tear down environments for projects. As for agents I want to be able to quickly deploy new ideas. That is in part acheived by my job framework wich is the follow on project to this one, but I need first and foremost have the secure base infrastructure in which to deploy my agent framework and agent resources. I also spin up separate environments for each penetration tests so one test cannot affect another. If I am running AI agents in an enviroment and they mess it up, I can tear down the whole environment and rebuild it easily. In addition, it ensures that my agents cannot affect production resources with proper security boundaries. When something is deployed incorrectly or I have a billing issue I cannot fix, I can tear down the environment to stop the biling and build a new one.

A full series on what I am developing in this project can be found here:

https://teriradichel.substack.com/p/toc-aws-organizations-and-ai-agent

## Tools and models

I'm primarily using Kiro CLI and anthropic models, though I do use Google aimode to ask questions at times and may branch out to test other models and technologies after this infrastructure is up and running.

## Issues:

https://github.com/2ndSightLab/ai-tracker/blob/main/issues.md

## AWS Wishlist

https://github.com/2ndSightLab/ai-tracker/blob/main/awswishlist.md

## Time

I started this project around March 7th. I had to take a break for about three weeks in May. I haven't really worked on anyting else besides this and blog posts because I keep thinking it is "almost done." I've also been working kind of long hours to do it and figure things out.

My initial post on this project tracks the start project and initial progress in 2.5 weeks

https://teriradichel.substack.com/p/what-ive-vibe-coded-in-25-weeks

The time it takes is demonstrated by feature completion and the timestapms in this GitHub repo, though my time may be taken away for other things periodically. 

## Cost: ##

Token and infrastructure spend.

| March | April | May |
| :---: | :---: | :---: | 
| $ | $ | $ |

Note that cost includes some times when the model was nerfed, billing snafus, and I took most of May off (though my plan rolled over and charged me even though I cancelled it before a trip.)

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

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Configure Role Profile | N/A | N/A | N/A | 🟢 | 🟢 | 🟢 |
| Assume Role With MFA | N/A | N/A | N/A | 🟢 | 🟢 | 🟢 |

### UI ##

Separate reusable project that handles configuring role profiles and role assumption with MFA.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Reusaable Numbered Menu with Filter by letters | N/A | N/A | N/A | 🟢 | 🔴 | 🔴 |
| Reusable y/n/e prompt | N/A | N/A | N/A | 🟢 | 🔴 | 🔴 |
| Step completion prompt | N/A | N/A | N/A | 🟡 | 🔴 | 🔴 |

### Base Environment ###

Resources installed in every environment. Some are optinoal.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Environment (all resources) | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| OU | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Accounts | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Move accounts to OU | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Account aliases | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| IPAM pool | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| IPAM EIP allocation | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| SCPs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin users | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin user policy | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin roles | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin role policy | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| S3 buckets (no KMS) | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS keys | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS policies | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| KMS key aliases | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deploy Lambdas | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| VPC Flow Logs Role | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Remote Access VPC | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Remote Access Subnet | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Remote Access Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Remote Access Internet Gateway | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Rmemote Access Route Table | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Rmemote Access Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Remote Access VPC Ram Shares | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment VPC | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deplopyment Subnet | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment Internet Gateway | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment Route Table | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment VPC Ram Shares | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment VPC Endpoints | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deployment VPC Endpoints SGs | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Delete default VPCs | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Lambdas (with VPC) | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| S3 buckets (with KMS) | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Bucket policies | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| SSH Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| RDP Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| HTTP/HTTPS Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu Instance Role | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu ENI | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu Instance | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu AMI | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| External AMI Share Key | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Share AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Budgets | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |

### Management Environment ###

The management environment contains accounts where my organization deletegated administrators exist.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Organization | 🔴 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Accounts: IAM, Network, Accounting, Org, Security, KMS, Security, Backup | 🟡 | 🔴 | 🟡  | 🔴 | 🔴 | 🔴 |
| Org resource policy | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate IPAM admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
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
| IPAM | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| AWS Prefix Lists | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Configure GuardDuty | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Security Hub | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure CloudTrail | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure AWS Config | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Macie | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Inspector | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure IAM Access Analyzer | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Security Alerts | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Deny-All OU | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Enable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Disable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### SCPs ##

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| kms-account-allowed-services [env] | 🟢  | 🔴 | 🟢  | 🔴 | 🔴 | 🔴 |
| deny-external-access [env] | 🟢 | 🔴 | 🟢  | 🔴 | 🔴 | 🔴 |
| always-denied-actions [root] | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| allowed-regions [root]  | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| always-denied-actions [env] | 🟢 | 🔴 | 🟢  | 🔴 | 🔴 | 🔴 |
| always-denied-actions [account] | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| deny-leave-organization[root]  | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| always-default-org-rool [root] | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| deploy-scp-require-imdsv2.sh | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |

### Web Infrastructure ###

This is a separate project that allows deploying a static website in any web account in any enviroment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Static Web Site | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Test Infrastructure ###

Some enviroments may include penetration testing and security research resources.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Burp ENI | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Burp Instance Role | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Burp Instance | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Burp AMI | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab ENI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab Instance Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab Instance | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Job Framework Infrastructure ###

The job framework infrastructure allows me to quickly and securely run jobs. 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Git Credentials Secrets | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Auth Lambdas (no VPC) | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Run Lambdas (no VPC) | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| S3 buckets (no KMS) | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| KMS keys | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Lambdas (with VPC) | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| S3 buckets (with KMS) | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Bucket policies | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Instance Role | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Kiro CLI Identity Center | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Dev ENI | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Dev Instance | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Dev AMI | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job ENI | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Instance | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job AMI | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth VPC | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth Subnet | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth Security Group | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth Route Table | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth Lambda Security Groups | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth VPC Endpoints | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth VPC Endpoint SGs | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| DynamoDB | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job VPC | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Subnet | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Security Group | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Internet Gateway | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Route Table | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Security Group | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job VPC Endpoints | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Route 53 Hosted Zone | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| ACM Certificate | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| API Gateway | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| CNAME | 🟡  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Backup Infrastructure ###

Back up infrastructure segregated from other infrastructure


| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Backup OU | 🟢  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Backup Account Per Environment | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Backup Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Backup Job | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Security Checks ###

| Feature | Deploy | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: |:---: |
| IAM Acccess Analyzer | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Prowler / AWS Equivalent (To review) | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

