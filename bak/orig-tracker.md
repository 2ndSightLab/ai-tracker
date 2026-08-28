
## Bootrstrap Role

### Bootstrap Role Script 

Role, policy and permission boundary deployed in root management account in AWS CloudShell.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Role | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| Policy | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |
| Permission Boundary | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 |
| Trust policy with MFA and IP condition  | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 |

## Shared Code Projects

### AWS CLI Auth with MFA

Separate reusable project that handles configuring role profiles and role assumption with MFA.

I used some previously written code as a starting point in which the [role trust policies contain MFA and IPAddress conditions to assume the role and the user associated with the keys cannot do anything except asusme a role with MFA](https://github.com/2ndSightLab/aws-scripts/tree/main/scripts). I found at some point the CLI Auth code in my AI repos was modified to cache creds. I thought I removed that in the original repo. Do your own code review.

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Configure Role Profile | 🟢 | 🟢 | 🟢 |
| Assume Role With MFA | 🟢 | 🟡 | 🟡 |

### XML Parser

A generic XML parser project that can be used by any bash project to move error prone and vulnerability prone code to a spearate locked down project.

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| XML read by path | 🟢 | 🔴 | 🔴 |
| XML write by path | 🟢 | 🔴 | 🔴 |
| XML load by path | 🟢 | 🔴 | 🔴 |
| XML read by single value | 🟢 | 🔴 | 🔴 |
| XML write by single value | 🟢 | 🔴 | 🔴 |
| XML load by single value | 🟢 | 🔴 | 🔴 |

### Menus

Separate reusable project provides simple and xml driven menus for consistency and easy updates

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Reusaable Numbered Menu with Filter by letters | 🟢 | 🔴 | 🔴 |
| Reusable y/n/e prompt | 🟢 | 🔴 | 🔴 |
| XML data driven Menu | 🟢 | 🔴 | 🔴 |
| Multi-select menu | 🟢 | 🔴 | 🔴 |
| /c to return to previous menu | 🟢 | 🔴 | 🔴 |
| common banner with lines above and below and text between | 🟢 | 🔴 | 🔴 |

### AWS Command Runner

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Run AWS Command | 🟢 | 🔴 | 🔴 |
| Track Deployed Resources | 🟢 | 🔴 | 🔴 |
| Switch Role (org/acount) | 🟢 | 🔴 | 🔴 |

### Time tracker

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Analysis Report | 🟢 | 🔴 | 🔴 |
| Report time (logs per day) | 🟢 | 🔴 | 🔴 |
| Report mistake (logs per day) | 🟢 | 🔴 | 🔴 |
| Bug Report | 🟢 | 🔴 | 🔴 |
| Run all tests (all projects) | 🟢 | 🔴 | 🔴 |

### Global Requirements

| Feature | Done | 
| :--- | :---: | 
| Cross-Project Requiremetns and Logging | 🟢 |

### Test Runner

| Feature | Done | 
| :--- | :---: | 
| Run test for all projects | 🟢 | 

## Bootstrap Code

### Bootstrap Orchestrator

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
| Default Org (define backup env) | 🟢 | n/a | n/a | n/a | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Resource type Dependencies | 🟢 | 🟢 | 🟢 |🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Bootstrap / Account Role Resource Confit | 🟢 | 🟢 | 🟢 |🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |


### Configure Organization Types Actions ##

| Feature | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | 
| Management Environment - Type ID | 🟢 | 🔴 | 🔴 | 
| Backup Environment - Type ID | 🟢 | 🔴 | 🔴 | 
| View Settings XML | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - All | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Enviroments | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Accounts | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Per org/env resources | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Type descriptions | 🟢 | 🔴 | 🔴 |  
| Actions File (menus) | 🟢 | 🔴 | 🔴 | 

### Configure Organization ###

* Multiple enviroments of a single type can be created (Web-Dev, Web-Prod, etc.)
* Multiple accounts of the same type can be created (Pentest1, Pentest2, etc.)
* The resource list is pullled from the type configuration, not altered here.

| Feature | List | Add | Delete | Rename | Menus | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Organization | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Evironments | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🔴 | 🔴 |
| Environment Accounts | 🟢 | 🟢 | 🟢 | n/a | 🟢 | 🟢 | 🔴 | 🔴 |

### Configure Organization Actions ###

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | 
| Create CLI Profiles | 🟡 | 🟡 | 🔴 | 🔴 |
| Select CLI Profiles | 🟢 | 🟢 | 🔴 | 🔴 | 
| Test CLI Porfile | 🟢 | 🟢 | 🔴 | 🔴 | 
| Look up Org, Root, Acount ID | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Seettings | 🟢 | 🟢 | 🔴 | 🔴 | 
| Environment Settings | 🟡 | 🟡 | 🔴 | 🔴 | 
| List Available Account Resources | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - All | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Enviroments | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Accounts | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Per org/env resources | 🟢 | 🟢 | 🔴 | 🔴 | 
| Organization Diagram - Type descriptions | 🟢 | 🟢 | 🔴 | 🔴 | 
| Actions File (menus) | 🟢 | 🟢 | 🔴 | 🔴 |

### Deploy Actions ##

| Feature | Menus | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | 
| Select Organization | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 
| Deploy Org Resources | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |  
| Select Env | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deploy Env Resources | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Select Account | 🟢 | 🟢 | 🟢  | 🔴 | 🔴 |
| Deploy Account Resources | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deployed Resources Tracking | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deployed Resources Diagram | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deploy With Confirm | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deploy No Prompt | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Drift Actions 

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: 
| Drift Report | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Drift Delete Unauthorized Resources | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Drift Deploy Missing Resources | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 
### Deploy Org Resources ###

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Organization | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Enable All Features | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: env-allowed-regions [env] | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: IMDSV1 [env] | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: always-denied-actions [root] | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: always-default-org-root [root] | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: deploy-scp-require-imdsv2.sh [root] | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Env Resources ###

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| OU | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 
| SCP: deny-external-access | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP: account specific OU only allowing resources deployed | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| SCP: for different regions than org regions (more restrictive) | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Rename OU | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Account Resources - every account ###

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Accounts | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Move account to OU | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Account alias | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Admin roles  | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Admin role policy | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delete Default VPC | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Rename account, alias, email, name | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

## Deny All Environment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| OU | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Deny All SCP | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

## Test Environment

Environment where people log into EC2 instances.

### OU

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| OU | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| SCP | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 | 
| Accounts | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Budgets | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Delete Default VPCs | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Admin roles | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| log to security account | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### IAM Account

IAM users in work environment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| IAM User | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### KMS Account

KMS keys used in enviroment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| KMS keys | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| KMS policies | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| KMS key aliases | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Network Account

Network resources shared to environmeng via RAM

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| VPC Flow Logs Role | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Jobs VPC | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Jobs Subnet | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Jobs NACL | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Route Table + Routes | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| VPC Endpoints | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Vpc Endoint Security Groups | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Jobs VCP Flow Logs | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Jobs Ram Share | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Work VPC | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Work Subnet | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Work NACL | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Work Route Table + Routes | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Work IGW | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Work Ram Share | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Work VCP Flow Logs | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Jobs Auth VPC | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Jobs Auth Subnet | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Jobs Auth NACL | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Jobs Auth Route Auth Table + Routes | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Jobs AUth IGW | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Jobs Auth VCP Flow Logs | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Jobs Auth Ram Share | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Remote Access Prefix List | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| AWS Services Prefix Lists | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| SSH Security Group | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| RDP Security Group | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| HTTP/HTTPS Security Group | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Account: log to security account | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### AMI Account

Account where people log into EC2 instances.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Base Ubuntu AMI | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Base Amazon Linux AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Burp AMI | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Collab AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Kiro Dev AMI | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Claude Code Ami | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Codex Ami | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Repos Account

Account where people log into EC2 instances.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Code Commit Repo | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| ECR | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Work Account

Account where people log into EC2 instances.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| IPAM pool | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| IPAM EIP allocation | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| S3 buckets (with KMS) | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Bucket policies | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Kiro Dev ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Kiro Instance Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Kiro Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Burp ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Burp Instance Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Burp Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Collab ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Collab Instance Role | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Collab Instance | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |
| Claude Code Dev ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Claude Code Instance Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Claude Code Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Codex Dev ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Codex Instance Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Codex Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |

### Domains Account

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Web Account

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources || 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Webs | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 |
| log to security account | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Jobs Auth Account

If I use CloudFront have to allow us-east-1 for ACM Cert. Lock down when not acively making chanages.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Job Auth Lambdas | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Auth Lambda VPC Config | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| ACM Certificate | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| API Gateway | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| API Gateway CNAME | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| DynamoDB | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |

### Jobs Run Account

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| S3 buckets | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Job Instance Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Job ENI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Job EC2 Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Job AMI | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Job Run (other resources, lambdas, micro VMs? TBD) | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |

## Management Environment

The management environment contains accounts where my organization deletegated administrators exist.

### IAM Acount

IAM users in management environment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Account | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| IAM User | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Org Acount 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Org resource policy| 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Kiro Account

IAM users in work environment

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Acoount resources | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Identity Center (requires interaction) |  🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| Kiro (requires interaction) | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |

### IPAM Account (Network)

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Account | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate IPAM admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Firewall Manager admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Network Manager admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate VPC Reachability Analyzer admin  | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| IPAM | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Security Acount

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Account | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Security Hub admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate GuardDuty admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate CloudTrail admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate AWS Config admin  | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Macie admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Inspector admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate IAM Access Analyzer admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Audit Manager admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Health admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Detective admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| S3 Logs buckets (one per env) | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| S3 Logs bucket - with encryption | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure GuardDuty | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure Security Hub | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure CloudTrail | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure AWS Config | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure Macie | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure Inspector | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure IAM Access Analyzer | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Configure Security Alerts | 🟡 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |


### KMS Acount

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Account, Move to OU, Alias | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| KMS Log Key | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| KMS Log Key Alias | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| KMS Log Key Policy | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Accounting Acount 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Account, Move to OU, Alias | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Cost Optimization Hub admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Delegate Compute Optimizer admin | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |

### Org Acount 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Account, Move to OU, Alias | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| Org Policy (org delegated admin) | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |


### Jobs

| Feature | Run | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | 
| Deploy Web Site | 🔴 | 🔴 | 🔴 | 🔴 |
| IAM Acccess Analyzer Report | 🔴 | 🔴 | 🔴 | 🔴 |
| Prowler Report | 🔴 | 🔴 | 🔴 | 🔴 | 
| Enable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 | 
| Disable AWS default Org Role | 🔴 | 🔴 | 🔴 | 🔴 |
| Move website | 🔴 | 🔴 | 🔴 | 🔴 |
| Lock Environment (apply deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Unlock Environment (remove deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Lock Account (apply deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Unlock Account (remove deny-all SCP) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Transfer GitHub repo to Code Commit | 🔴 | 🔴 | 🔴 | 🔴 | 
| Transfer one Code Commit repo to Another | 🔴 | 🔴 | 🔴 | 🔴 | 
| Troubleshoot Job | 🔴 | 🔴 | 🔴 | 🔴 | 
| Analyze Network Traffic | 🔴 | 🔴 | 🔴 | 🔴 | 
| Analyze System Logs | 🔴 | 🔴 | 🔴 | 🔴 | 
| Move Domain | 🔴 | 🔴 | 🔴 | 🔴 | 
| Move Hosted Zone | 🔴 | 🔴 | 🔴 | 🔴 | 
| Register domain | 🔴 | 🔴 | 🔴 | 🔴 | 
| Update Parent Hosted Zone (specific steps TBD) | 🔴 | 🔴 | 🔴 | 🔴 | 
| Share all amis to all acounts in ou | 🔴  | 🔴 | 🔴 | 🔴 | 🔴 | 
| Share AMI To External | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 
| Archive Acount | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 


## Backup Environment

### Env OU

Back up infrastructure segregated from other infrastructure

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Backup OU | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| budgets | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| delete default vpcs | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |
| admin roles | 🟢 | 🟢 | 🟢 | 🟢 | 🔴 | 🔴 |
| log to security account | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

### Backup Admin Account
| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Delegate Backup admin | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |

### KMS Account

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Delegate Backup admin | 🟡 | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 |

### Backup Accounts

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Backup Account Per Environment | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 | 🔴 |

## Single Account Test Environment

### Single Account Resources To Run Jobs (?)

Deploy environment to single account (account in a different organization or standalone) 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Network | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| User | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Role | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
| Jobs Instance | 🟡 | 🟡 | 🟡 | 🔴 | 🔴 | 🔴 |
