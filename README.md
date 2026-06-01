# AI Tracker

## Objective

Track how long it takes and how much it costs to create projects with AI in an attempt to optimize progress.

## AWS Bootstrap Script for AI Agent Environment

This is a project to deploy resources to create AWS environments in an organization. I wnat to segregate the agents that are running from other resources in my AWS account. While I'm at it I want to deploy the security controls to manage my organization in a management environment. I started this project around March 7th. I had to take a break for abou three weeks in May. I haven't really worked on anyting else besides this and blog posts because I keep thinking it is "almost done." I've also been working kind of long hours to do it and figure things out.

https://teriradichel.substack.com/p/what-ive-vibe-coded-in-25-weeks

I'm writing about how I'm doing this here:

https://teriradichel.substack.com/p/toc-aws-organizations-and-ai-agent

This environment includes a Yubikey auth mechanism I'm trying to build and the instances I use for pentesting and bug bounties.

https://teriradichel.substack.com/p/mfa-to-run-a-lambda-function

I have multiple steps for amots every reasource: Deploy, Delete and Verifiy. I am tracking whether they are done below. I also indicate B if something broke when I made changes and I'm fixing it. Things break when I refactor the code to add new functionality or fix functional problems or other bugs.

## Cost: ##

Token and infrastructure spend.

| March | April | May |
| :---: | :---: | :---: | 
| $ | $ | $ |

Note that cost includes some times when the model was nerfed, billing snafus, and I took most of May off (though my plan rolled over and charged me even though I cancelled it before a trip.)

## Legend

N = Not Done Y = Done B = Broke N/A = not applicable for that resource.

### Management Environment ###

| Resource Name | Deploy | Delete | Verify | Tested |
| :--- | :---: | :---: | :---: | :---: |
| Environment | N | N | N | N | N |
| Resource | N | N | N | N | N |

### Jobs Environment ###

| Resource Name | Deploy | Delete | Verify | Tested |
| :--- | :---: | :---: | :---: | :---: |
| Environment | N | N | N | N | N |
| Resource | N | N | N | N | N |

### Test Environment ###

| Resource Name | Deploy | Delete | Verify | Tested |
| :--- | :---: | :---: | :---: | :---: |
| Environment | N | N | N | N | N |
| Resource | N | N | N | N | N |

### Prod Environment ###

| Resource Name | Deploy | Delete | Verify | Tested |
| :--- | :---: | :---: | :---: | :---: |
| Environment | N | N | N | N | N |
| Resource | N | N | N | N | N |

### Job Framework ###
| Resource Name | Deploy | Delete | Verify | Tested |
| :--- | :---: | :---: | :---: | :---: |
| Yubikey Lambda | N | N | N | N | N |
| Lambda Layer | N | N | N | N | N |
| Lambda Layer | N | N | N | N | N |

