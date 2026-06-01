# AI Tracker

## Objective

Track how long it takes and how much it costs to create projects with AI in an attempt to optimize progress.

## Support this research

If you want to support of follow this research consider becoming a paid subscriber on my substack blog. Paid subscribers can add comments. Founding members can ask questions (i.e. consulting or training). You can also just sign up for free - no worries! All are welcome and appreciated. 🩵

https://teriradichel.substack.com

## Project Objective: AWS Bootstrap Script for AI Agent Environment 

Build a script to deploy, delete, and test an AWS environment to securely run AI agents. This includes my organizational framework and security controls to segregate environemnts and monitor AWS activity. Specifically I want to segregate my security testing, development, production, and management environments. The framework also sets up my organization with monitoring including budgets and security services used by delegated administrators (Guard Duty, etc.)

The whole point of this is to be able to quickly spin up and tear down environments for projects. As for agents I want to be able to quickly deploy new ideas. That is in part acheived by my job framework wich is the follow on project to this one, but I need first and foremost have the secure base infrastructure in which to deploy my agent framework and agent resources. I also spin up separate environments for each penetration tests so one test cannot affect another. If I am running AI agents in an enviroment and they mess it up, I can tear down the whole environment and rebuild it easily. In addition, it ensures that my agents cannot affect production resources with proper security boundaries. When something is deployed incorrectly or I have a billing issue I cannot fix, I can tear down the environment to stop the biling and build a new one.

A full series on what I am developing in this project can be found here:

https://teriradichel.substack.com/p/toc-aws-organizations-and-ai-agent

## Time

I started this project around March 7th. I had to take a break for about three weeks in May. I haven't really worked on anyting else besides this and blog posts because I keep thinking it is "almost done." I've also been working kind of long hours to do it and figure things out.

My initial post on this project tracks the start project and initial progress in 2.5 weeks

https://teriradichel.substack.com/p/what-ive-vibe-coded-in-25-weeks

## Cost: ##

Token and infrastructure spend.

| March | April | May |
| :---: | :---: | :---: | 
| $ | $ | $ |

Note that cost includes some times when the model was nerfed, billing snafus, and I took most of May off (though my plan rolled over and charged me even though I cancelled it before a trip.)

## Objectives

N = Not Done Y = Done B = Broke N/A = not applicable for that resource.

### Management Environment ###

The management environment contains accounts where my organization deletegated administrators exist.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Environment | N | N | N | N | N | N | N |
| Resource | N | N | N | N | N | N | N |
| TODO | N | N | N | N | N | N | N |

### Jobs Environment ###

The jobs environment is where I can deploy and test jobs and agents.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Environment | N | N | N | N | N | N | N |
| Resource | N | N | N | N | N | N | N |
| TODO | N | N | N | N | N | N | N |

### Prod Environment ###

The production environment is where I run production applications and websites.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Environment | N | N | N | N | N | N | N |
| Resource | N | N | N | N | N | N | N |
| TODO | N | N | N | N | N | N | N |

### Test Infrastructure ###

Some enviroments may include penetration testing and security research resources.

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Environment | N | N | N | N | N | N | N |
| Resource | N | N | N | N | N | N | N |
| TODO | N | N | N | N | N | N | N |

### Job Framework Infrastructure ###

The job framework infrastructure allows me to quickly and securely run jobs. 

| Feature | Deploy | Delete | Verify | Tested | Code Review | Security Review |
| :--- | :---: | :---: | :---: | :---: | :---: |:---: |
| Yubikey Lambda | N | N | N | N | N | N | N |
| Lambda Layer | N | N | N | N | N | N | N |
| API Gateway | N | N | N | N | N | N | N |
| TODO | N | N | N | N | N | N | N |

