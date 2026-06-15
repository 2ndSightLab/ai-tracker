# AI Tracker

## Objective

Track how long it takes and how much it costs to create projects with AI 🤖 in an attempt to optimize progress.

| Month | Plan | usage | charges |
| :---:| :---: | :---: | :---: |
| June 1-12 | $200 plan | maxed | $83 |
| June 13-15 | $200 plan | +80% | ? |

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
**Date Range:** Mar 7, 2026 - Jun 12, 2026

| Service / Category | Total | Mar 2026 | Apr 2026 | May 2026 | Jun 2026* |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Total costs** | **$1,571.19** | **$359.07** | **$387.55** | **$621.52** | **$203.04** |
| Kiro | $692.19 | $193.55 | $129.07 | $285.79 | $83.77 |
| Virtual Private Cloud | $344.92 | $50.07 | $118.34 | $137.58 | $38.94 |
| Elastic Compute Cloud - Compute | $222.59 | $39.45 | $44.28 | $100.12 | $38.74 |

Costs broken down by service can be found here:

https://github.com/2ndSightLab/ai-tracker/blob/main/cost.md

This data is pulled from a custom Dashboard I created in the AWS Cost Management serivce in the AWS Console. I copy and paste the data into Google aimode, translate it to markdown, and paste it here periodically. Note that the organizational costs include monitoring for a few other accounts that contain static websites, storage and where I do some security research and pentesting. Those account costs are not included but the cost of the organizational services includes those other accounts. I didn't bother to try to filter that out due to lack of time and I'm not sure how to do that wihtout looking into it further. The cost is minimal and not worth the effort at them moment. Also note there was a billing snafu in the month of May for which I did not get credit. There were $200 of tokens I could not use at all in that month. I had to go help a hurt family member and shut down the plan before I left but somehow when I got back it was still active and I got billd for another month. I had a knee-jerk reaction when I saw it and shut it down right away to stop the billing. I still got billed for it even though I didn't use it at all. So don't do that.

## Objectives

### Status Legend ###

| Status | Description | 
| :--- | :---: | 
| 🟢 | Done |
| 🟡 | Broke or Implmeented Not Yet Run |
| 🔴 | Not Done |

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

I used some previously written code as a starting point in which the [role trust policies contain MFA and IPAddress conditions to assume the role and the user associated with the keys cannot do anything except asusme a role with MFA](https://github.com/2ndSightLab/aws-scripts/tree/main/scripts). I found at some point the CLI Auth code in my AI repos was modified to cache creds. I thought I removed that in the original repo. Do your own code review.

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Configure Role Profile | 🟢 | 🟢 | 🟢 |
| Assume Role With MFA | 🟢 | 🟡 | 🟡 |

### XML Parser ###

A generic XML parser project that can be used by any bash project to move error prone and vulnerability prone code to a spearate locked down project.

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| XML read by path | 🟢 | 🔴 | 🔴 |
| XML write by path | 🟢 | 🔴 | 🔴 |
| XML load by path | 🟢 | 🔴 | 🔴 |
| XML read by single value | 🟢 | 🔴 | 🔴 |
| XML write by single value | 🟢 | 🔴 | 🔴 |
| XML load by single value | 🟢 | 🔴 | 🔴 |

### Common Menus ###

Separate reusable project provides simple and xml driven menus for consistency and easy updates

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Reusaable Numbered Menu with Filter by letters | 🟢 | 🔴 | 🔴 |
| Reusable y/n/e prompt | 🟢 | 🔴 | 🔴 |
| XML data driven Menu | 🟢 | 🔴 | 🔴 |
| Multi-select menu | 🟢 | 🔴 | 🔴 |
| /c to return to previous menu | 🟢 | 🔴 | 🔴 |
| common banner with lines above and below and text between | 🟢 | 🔴 | 🔴 |

### Bootstrap Orchestrator Project ##

A project to manaage te handoff from org to environnet project so neither depends on the other.
Reduces context and scope of the org and environment projects.

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Configure Org Types (Menu Action)  | 🟢 | 🔴 | 🔴 |
| Configure Org (Menu Action)  | 🟢 | 🔴 | 🔴 |
| Deploy Resources (Menu Action) | 🟢 | 🔴 | 🔴 |
| Manage Drift (Menu Action) | 🟢 | 🔴 | 🔴 |

### Configure Organization Types ##

Configure organization to deploy; define environemnt types (allowed resources)

* Environment Types Define accounts and resources that can be deployed to an environment.
* Accounts define resources that can be deployed to account on top of environmen resources.
* The resource master list maps a reosurce to a script that deploys it (to create a menu of resources to deploy)

| Feature | List | Add | Delete | Rename | Edit | Menus | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Resource Types | 🟢 | 🟢 | 🟢 | 🟢| n/a | 🟢 | 🟢 | 🔴 | 🔴 |
| Account Types | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Account Resource Types | 🟢 | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🔴 | 🔴 |
| Environment Types | 🟢 | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🔴 | 🔴 |
| Environment Type Account Types | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Environment Type Resource Types | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Default Org (define mangemnt env) | 🟢 | n/a | n/a | n/a | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Configure Organization ###

* Multiple enviroments of a single type can be created (Web-Dev, Web-Prod, etc.)
* Multiple accounts of the same type can be created (Pentest1, Pentest2, etc.)
* The resource list is pullled from the type configuration, not altered here.

| Feature | List | Add | Delete | Rename | Menus | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Organization | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Evironments | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🔴 | 🔴 |
| Environment Accounts | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🔴 | 🔴 |

### Configure Actions ###

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | 
| Create CLI Profiles | 🟡 | 🟡 | 🔴 | 🔴 |
| Select CLI Profiles | 🟢 | 🟢 | 🔴 | 🔴 | 
| Test CLI Porfile | 🟢 | 🟢 | 🔴 | 🔴 | 
| Look up Org, Root, Acount ID | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Seettings | 🟢 | 🟢 | 🔴 | 🔴 | 
| Environment Settings | 🔴 | 🔴 | 🔴 | 🔴 | 
| List Available Account Resources | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - All | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Enviroments | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Accounts | 🟢 | 🟢 | 🔴 | 🔴 | 

### Deploy ##

| Feature | Menus | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: 
| Select Organization | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 
| Deploy Org Resources | 🟢 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Select Env |  🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Deploy Env Resources |  🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Select Account | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Deploy Account Resources | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 


### Base Environment Resources ###

Resources installed in every environment. Some are optinoal.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Environment (OU) | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Accounts: IAM, KMS, Backup (in backup OU) | 🟢 | 🔴 | 🟢 | 🟢 | 🔴 | 🔴 |
| Move accounts to OU | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| Account aliases | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| Admin users | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin user policy | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin roles | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Admin role policy | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Deployment Lambdas | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| S3 Logs bucket | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Logs KMS key | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: kms-account-allowed-services [env] | 🟢 | 🟢 | 🟢  | 🔴 | 🔴 | 🔴 |
| SCP: deny-external-access [env] | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: always-denied-actions [env] | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: env-allowed-regions [env]  | 🟡 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |

### Management Environment Resources ###

The management environment contains accounts where my organization deletegated administrators exist.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Organization | 🟢 | 🔴 | 🟢 | 🟢  | 🔴 | 🔴 |
| Enable Org all features | 🟢 | 🟡 | 🟢 | 🟢  | 🔴 | 🔴 |
| Accounts: IAM, IPAM, Accounting, Org, Security, KMS, Security, Backup (in backup OU) | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| Org resource policy | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate IPAM admin | 🟢 | 🟡 | 🟢 | 🟢  | 🔴 | 🔴 |
| Delegate Security Hub admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate GuardDuty admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate CloudTrail admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate AWS Config admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Firewall Manager admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Macie admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Inspector admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate IAM Access Analyzer admin | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Audit Manager admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Health admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Detective admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Backup admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Network Manager admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate VPC Reachability Analyzer admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Cost Optimization Hub admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Delegate Compute Optimizer admin | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| IPAM | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| Root SCPs | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| AWS Prefix Lists | 🟢 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 |
| Configure GuardDuty | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Security Hub | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure CloudTrail | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure AWS Config | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Macie | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure Inspector | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Configure IAM Access Analyzer | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Deny-All OU | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: always-denied-actions [root] | 🟢 | 🟢  | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: deny-leave-organization[root]  | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| SCP: always-default-org-root [root] | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: deploy-scp-require-imdsv2.sh [root] | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Environment SCPs | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: deny-all [account or OU] | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 
| SCP: org-allowed-regions [root]  | 🟡 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| Configure Security Alerts | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |


### Backup Environment ###

Back up infrastructure segregated from other infrastructure

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Backup OU | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Account Per Environment | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Archive Account Lambda Role | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Archive Account Lambda | 🟢 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 |
| Archive Account Lambda SG | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Backup VPC | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Subnet | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Security Group | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Route Table | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup Lambda Security Groups | 🟢  | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Backup VPC Endpoints | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup VPC Endpoint SGs | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Backup VPC RAM share | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Bacup VPC Flowlogs | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |


### Domains Envirnoment ( Base Environment +) ###

Domain name management. One for prod and one for test in my case. 
Can lock when not in use with deny all SCP.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: dns (no backup) | 🟡 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |


### Work Environment Resources ( Base Environment +) ###

Environment where people log into EC2 instances.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: work, amis, backup | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| IPAM pool | 🟢 | 🟡  | 🟢 | 🟢 | 🔴 | 🔴 |
| IPAM EIP allocation | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Environment SCPs | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| S3 buckets (no KMS) | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS keys | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS policies | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS key aliases | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| VPC Flow Logs Role | 🟢 | 🟡 | 🟢| 🔴 | 🔴 | 🔴 |
| Remote Access Prefix List | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
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
| S3 buckets (with KMS) | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Bucket policies | 🟢 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 |
| SSH Security Group | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| RDP Security Group | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| HTTP/HTTPS Security Group | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Budgets | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu Instance Role | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu ENI | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu Instance | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Ubuntu AMI | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Base Amazon Linux Instance Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Amaxon Linux ENI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Amazon Linux Instance | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Base Amazon Linux AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Management Environment Actions ###

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: |
| IAM Acccess Analyzer Report | 🟡 | 🔴 | 🔴 | 🔴 |
| Prowler Report | 🔴 | 🔴 | 🔴 | 🔴 | 
| Enable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 | 
| Disable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 |
| Move website | 🔴 | 🔴 | 🔴 | 🔴 |
| Lock Environment (apply deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Unlock Environment (remove deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Lock Account (apply deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Unlock Account (remove deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 

### Web Environment ( Base Environment +) ###

This environment is used to host static websites and web applications.
I have a separate project that allows deploying a static website in any web account in any enviroment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: web, backup | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deploy Web Lambda | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 |

### Kiro management environment (Base Environment +) ###

Separaete environment because it reuqires us-east-1. Manage Kiro subscriptions.
Also separates account from specific projects or activities.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Account (kiro mangement) | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Kiro | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Standalone Identity Center | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| SCP: kiro-identity-center-only | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| SCP for us-east-1 only | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |

### Jobs Auth Environment (Web Environment, +) ###

If I use CloudFront have to allow us-east-1 for ACM Cert. Lock down when not acively making chanages.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts (web, backup)| 🟡 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Auth Lambdas | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Lambda VPC Config | 🟡 | 🟢 | 🟡 | 🔴 | 🔴 | 🔴 |
| ACM Certificate | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| API Gateway | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| API Gateway CNAME | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| DynamoDB | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| SCP for us-east-1 only | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |

### Jobs Run Environment (Work Environment, Web Environment, +) ###

The job framework infrastructure allows me to quickly and securely run jobs which could include AI agents.
I have a separate set of projects for the Job and AI agent application layer framework and job infrastructure.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: jobs | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| Job VPC | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Subnet | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Security Group | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Internet Gateway | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Route Table | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job Security Group | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job VPC Endpoints | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job RAM Share | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 | 🔴 |
| Job VPC Flow Logs | 🟢 | 🔴 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Subnet | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Security Group | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Route Table | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth Lambda Security Groups | 🟢 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 |
| Auth VPC Endpoints | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC Endpoint SGs | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC RAM share | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Auth VPC Flowlogs | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| S3 buckets (no KMS) | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| KMS keys | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Git Credentials Secrets | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Dev Instance Role | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Dev ENI | 🟢 | 🟡 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Dev EC2 Instance | 🟢 | 🟡 | 🟢  | 🔴 | 🔴 | 🔴 |
| Job Dev AMI | 🟢 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 |
| Route 53 Hosted Zone | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |
| Job Run Lambdas | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 🔴 |

### Test Environment (Work Environment, Web Environment, Jobs Environment, +) ###

Some enviroments may include penetration testing and security research resources.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Accounts: project | 🟢 | 🟡 | 🟢 | 🟢 | 🔴 | 🔴 |
| Burp ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Burp Instance Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Burp Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Burp AMI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Collab ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Collab Instance Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab Instance | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

( And other stuff not shown here :^) 

### Single Account Test Environment ##

Deploy environment to single account (account in a different organization or standalone) 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Network | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| User | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Jobs Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |

### Drift ##

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: 
| Drift Report | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Drift Delete Unauthorized Resources | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Drift Deploy Missing Resources | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 

### DNS Environment Actions ###

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Move Domain | 🟢 | 🟢 | 🔴 |
| Move Hosted Zone | 🟢 | 🔴 | 🔴 |
| Register domain | 🟡 | 🔴 | 🔴 | 
| Update Parent Hosted Zone (specific steps TBD) | 🔴 | 🔴 | 🔴 | 

### AMI Account Actions ###

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: |
| Share all amis to all acounts in ou | 🟡 | 🔴 | 🔴 | 🔴 | 
| Share AMI To External | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Repo Account Actions ###

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: |
| Transfer GitHub repo to Code Commit | 🔴 | 🔴 | 🔴 | 🔴 | 
| Transfer one Code Commit repo to Another | 🔴 | 🔴 | 🔴 | 🔴 | 

### KMS Account Actions ###

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: |
| Deploy External AMI Share Key | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Web Environment Actions ###

Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Deploy Static Website | 🔴 | 🔴 | 🔴 | 🔴 | 

### Backup Environment Actions ###

Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Archive Acount | 🔴 | 🔴 | 🔴 | 🔴 | 

### Manage Organization Environment ###

* Manage enviroment resources as a group
  
| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Select Environment | 🟡 | 🔴 | 🔴 |
| Deploy all resources | 🟡 | 🟡 | 🔴 | 
| Auto-gen env SCP | 🔴 | 🔴 | 🔴 |
| Auto-gen account SCP | 🔴 | 🔴 | 🔴 |
| Delete all resources | 🔴 | 🔴 | 🔴 | 
| View all resources | 🔴 | 🔴 | 🔴 | 
