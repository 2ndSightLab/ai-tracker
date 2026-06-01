# AI Tracker

## Objective

Track how long it takes and how much it costs to create projects with AI 🤖 in an attempt to optimize progress.

## Support this research

If you want to support of follow this research consider becoming a paid subscriber on my substack blog. Paid subscribers can add comments. Founding members can ask questions (i.e. consulting or training). You can also just sign up for free - no worries! All are welcome and appreciated. 🩵

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

N = Not Done Y = Done B = Broke N/A = not applicable for that resource.

### Bootstrap Role ###

Role, policy and permission boundary deployed in root management account in AWS CloudShell.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Role | Y | Y | Y | Y | Y | Y |
| Policy | Y | Y | Y | Y | Y | Y |
| Permission Boundary | Y | Y | Y | Y | Y | Y |
| Trust policy with MFA and IP condition  | Y | Y | Y | Y | Y | Y |

### Base Environment ###

Resources installed in every environment. Some are optinoal.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| OU | Y | N | Y | N | N | N |
| Accounts | Y | N | Y | N | N | N |
| Move accounts to OU | Y | N | Y | N | N | N |
| Account aliases | Y | N | Y | N | N | N |
| IPAM pool | B | N | Y | N | N | N |
| IPAM EIP allocation | B | N | Y | N | N | N |
| SCPs | Y | N | Y | N | N | N |
| Admin users | Y | N | Y | N | N | N |
| Admin user policy | Y | N | N | N | N | N |
| Admin roles | Y | N | N | N | N | N |
| Admin role policy | Y | N | N | N | N | N |
| S3 buckets (no KMS) | N | N | N | N | N | N |
| KMS keys | N | N | N | N | N | N |
| KMS key aliases | N | N | N | N | N | N |
| KMS policies | N | N | N | N | N | N |
| AWS Prefix Lists | N | N | N | N | N | N |
| Deploy S3 Bucket Lambda | N | N | N | N | N | N |
| Deploy S3 SG | N | N | N | N | N | N |
| Deploy Netork Lambda | N | N | N | N | N | N |
| Deploy Netork SG | N | N | N | N | N | N |
| VPC Flow Logs Role | N | N | N | N | N | N |
| Remote Access VPC | N | N | N | N | N | N |
| Remote Access Subnet | N | N | N | N | N | N |
| Remote Access Security Group | N | N | N | N | N | N |
| Remote Access Internet Gateway | N | N | N | N | N | N |
| Rmemote Access Route Table | N | N | N | N | N | N |
| Rmemote Access Security Group | N | N | N | N | N | N |
| Remote Access VPC Ram Shares | N | N | N | N | N | N |
| Deployment VPC | N | N | N | N | N | N |
| Deplopyment Subnet | N | N | N | N | N | N |
| Deployment Security Group | N | N | N | N | N | N |
| Deployment Internet Gateway | N | N | N | N | N | N |
| Deployment Route Table | N | N | N | N | N | N |
| Deployment Security Group | N | N | N | N | N | N |
| Deployment VPC Ram Shares | N | N | N | N | N | N |
| Deployment VPC Endpoints | N | N | N | N | N | N |
| Deployment VPC Endpoints SGs | N | N | N | N | N | N |
| Delete default VPCs | N | N | N | N | N | N |
| Lambdas (with VPC) | N | N | N | N | N | N |
| S3 buckets (with KMS) | N | N | N | N | N | N |
| Bucket policies | N | N | N | N | N | N |
| SSH Security Group | N | N | N | N | N | N |
| RDP Security Group | N | N | N | N | N | N |
| HTTP/HTTPS Security Group | N | N | N | N | N | N |
| Base Ubuntu Instance Role | N | N | N | N | N | N |
| Base Ubuntu ENI | N | N | N | N | N | N |
| Base Ubuntu Instance | N | N | N | N | N | N |
| Base Ubuntu AMI | N | N | N | N | N | N |
| External AMI Share Key | N | N | N | N | N | N |
| Share AMI | N | N | N | N | N | N |
| Budgets | N | N | N | N | N | N |

### Management Environment ###

The management environment contains accounts where my organization deletegated administrators exist.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Org resource policy | N | N | N | N | N | N |
| Delegate IPAM admin | N | N | N | N | N | N |
| Delegate Security Hub admin | N | N | N | N | N | N |
| Delegate GuardDuty admin | N | N | N | N | N | N |
| Delegate CloudTrail admin | N | N | N | N | N | N |
| Delegate AWS Config admin | N | N | N | N | N | N |
| Delegate Firewall Manager admin | N | N | N | N | N | N |
| Delegate Macie admin | N | N | N | N | N | N |
| Delegate Inspector admin | N | N | N | N | N | N |
| Delegate IAM Access Analyzer admin | N | N | N | N | N | N |
| Delegate Audit Manager admin | N | N | N | N | N | N |
| Delegate Health admin | N | N | N | N | N | N |
| Delegate Detective admin | N | N | N | N | N | N |
| Delegate Backup admin | N | N | N | N | N | N |
| Delegate Network Manager admin | N | N | N | N | N | N |
| Delegate VPC Reachability Analyzer admin | N | N | N | N | N | N |
| Delegate Cost Optimization Hub admin | N | N | N | N | N | N |
| Delegate Compute Optimizer admin | N | N | N | N | N | N |
| IPAM | N | N | N | N | N | N |
| Configure GuardDuty | N | N | N | N | N | N |
| Configure Security Hub | N | N | N | N | N | N |
| Configure CloudTrail | N | N | N | N | N | N |
| Configure AWS Config | N | N | N | N | N | N |
| Configure Macie | N | N | N | N | N | N |
| Configure Inspector | N | N | N | N | N | N |
| Configure IAM Access Analyzer | N | N | N | N | N | N |
| Configure Security Alerts | N | N | N | N | N | N |
| Deny-All OU | N | N | N | N | N | N |

### Web Infrastructure ###

The production environment is where I run production applications and websites.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Static Web Site | N | N | N | N | N | N |

### Test Infrastructure ###

Some enviroments may include penetration testing and security research resources.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Burp ENI | N | N | N | N | N | N |
| Burp Instance Role | N | N | N | N | N | N |
| Burp Instance | N | N | N | N | N | N |
| Burp AMI | N | N | N | N | N | N |
| Collab ENI | N | N | N | N | N | N |
| Collab Instance Role | N | N | N | N | N | N |
| Collab Instance | N | N | N | N | N | N |
| Collab AMI | N | N | N | N | N | N |

### Job Framework Infrastructure ###

The job framework infrastructure allows me to quickly and securely run jobs. 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Git Credentials Secrets | N | N | N | N | N | N |
| Deploy Lambdas (no VPC) | N | N | N | N | N | N |
| S3 buckets (no KMS) | N | N | N | N | N | N |
| KMS keys | N | N | N | N | N | N |
| Lambdas (with VPC) | N | N | N | N | N | N |
| S3 buckets (with KMS) | N | N | N | N | N | N |
| Bucket policies | N | N | N | N | N | N |
| Job Instance Role | N | N | N | N | N | N |
| Kiro CLI Identity Center | N | N | N | N | N | N |
| Job Dev ENI | N | N | N | N | N | N |
| Job Dev Instance | N | N | N | N | N | N |
| Job Dev AMI | N | N | N | N | N | N |
| Job ENI | N | N | N | N | N | N |
| Job Instance | N | N | N | N | N | N |
| Job AMI | N | N | N | N | N | N |
| Auth VPC | N | N | N | N | N | N |
| Auth Subnet | N | N | N | N | N | N |
| Auth Security Group | N | N | N | N | N | N |
| Auth Internet Gateway | N | N | N | N | N | N |
| Auth Route Table | N | N | N | N | N | N |
| Auth Lambda Security Groups | N | N | N | N | N | N |
| Auth VPC Endpoints | N | N | N | N | N | N |
| Auth VPC Endpoint SGs | N | N | N | N | N | N |
| DynamoDB | N | N | N | N | N | N |
| Auth Lambdas (With VPC) | N | N | N | N | N | N |
| Job Base Lambda (With VPC) | N | N | N | N | N | N |
| Job VPC | N | N | N | N | N | N |
| Job Subnet | N | N | N | N | N | N |
| Job Security Group | N | N | N | N | N | N |
| Job Internet Gateway | N | N | N | N | N | N |
| Job Route Table | N | N | N | N | N | N |
| Job Security Group | N | N | N | N | N | N |
| Job VPC Endpoints | N | N | N | N | N | N |
| Route 53 Hosted Zone | N | N | N | N | N | N |
| ACM Certificate | N | N | N | N | N | N |
| API Gateway | N | N | N | N | N | N |
| CNAME | N | N | N | N | N | N |

### Backup Infrastructure ###

Back up infrastructure segregated from other infrastructure

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Backup Account Per Environment | N | N | N | N | N | N |
| Backup Role | N | N | N | N | N | N |
| Backup Job | N | N | N | N | N | N |

