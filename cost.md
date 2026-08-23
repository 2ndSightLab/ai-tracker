# Costs while building an AI Agent Bootstrap Script and Framework

A couple of years ago Werner Vogels did a whole talk on looking at the cost of your architecture which I loved. So that's what I'm doing here.

### 8/23/2026

Just logged into Claude Code and realized it has screen for Claude Code in API usage mode. It shows cost and lines accepted. I've written before that lines accepted is meaningless because sometimes you have to accept the lines and then test and you find out after it's done that their wrong and have to fix them. So that is not really a true tracker of efficiency of an AI model. 

A better question is ... what has it completed that is usable and useful? How much did it cost and how much time did it take to get to that point?

By the way to answer the question if Fable is better I'd say depends what you are doing. For small stuff it is a waste of time and get things wrong anyway. But it seems like if I'm troubleshooting a tricky cross project but of some kind complex bugs where the model is banging it's head against a wall it seems it might help. But sometimes in those cases I just to dig in more myself. Overall I rarely use it.

### 8/15/2026

I am looking at Bedrock pricing compared to Anthropic direct pricing:


| Model | Input | Output | Input (Batch) | Output (Batch) | Input (5m Cache Write) | Input (1h Cache Write) | Input (Cache Read) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | $5.00 | $25.00 | $2.50 | $12.50 | $6.25 | $10.00 | $0.50 |
| **Claude Sonnet 5** | $2.00 | $10.00 | N/A | N/A | $2.50 | $4.00 | $0.20 |
| **Claude Fable 5** | $10.00 | $50.00 | N/A | N/A | $12.50 | $20.00 | $1.00 |
| **Claude Opus 4.8** | $5.00 | $25.00 | N/A | N/A | $6.25 | $10.00 | $0.50 |

I asked google/aimode which is cheaper. I haven't verified or tested it but here's what it says:

If you are running short prompts under 200K tokens or heavily using asynchronous batches, switching to the direct Anthropic API will be identical or slightly cheaper. However, if you regularly use massive prompts over 200K tokens, staying with a provider that skips the 2x long-context surcharge will save you significant money.

Well, in my case I do short prompts switching between agents all the time. So does that mean Anthropic is cheaper in that case? That's when I do autonomous programming. But what about when I'm just chatting? Sometimes my conversations get lengthy. Hmm. IDK. More testing is needed.

Also, is Fable 5 really that much better???

### 2026-08-15 3:13 PM

Kicked off five agents to fix the related projects according to those instructions...running....but then i set only ONE project to ultrathink and IMMEDIATELY ran out of credits. In the past I had 2-3 projects running in ultrathink and this did not happen. I don't understand this at all. I only changed some requirements, kicked off the agents, and I'm already out of credits.

### 8/15/2026 2:07 AM

I don't understand Anthropic credits yet. At some point tonight said I had used 90% of my credits/tokens whatever. I had just started. Then it reset before I even stopped and I was working again. I worked from afternoon sometime till about midnight or 1 a.m.

I'm still on the same $50 plan I think. Haven't gotten into my API credits yet. So how does this work anyway? I've been working since August 13th. Let's check usage. Apparently you can do that the same way you can do on Kiro: /usage

I dont know how to control subagent spawning. Maybe something to look into. I don't care I just want it to get the problem solved correctly. Can we please just focus on that? I mean if you get the problem right in the first place it won't use as many tokens right? So spawn whatever agents are needed to get it done correctly and quickly. Maybe I'll look into that later.

Note that it says Sonnet below but I've mostly used Opus 5. I have avoided Fable because it costs usage credits but will try it through another option I have later. Looks like my session is working again. But it's time for bed...

```

 ▐▛███▜▌   Claude Code v2.1.231
▝▜█████▛▘  Sonnet 5 · Claude Team
▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔
   Settings  Status   Config   Usage   Stats
   
   Session
   
   Total cost:            $0.0000
   Total duration (API):  0s
   Total duration (wall): 6s
   Total code changes:    0 lines added, 0 lines removed
   Usage:                 0 input, 0 output, 0 cache read, 0 cache write
   
   Current session
                                                      0% used
   
   Current week (all models)
   ██████████████████████████▌                        53% used
   Resets Aug 18, 1am (UTC)
   +50% weekly limits promo through Aug 19 · clau.de/cc-50-promo
   
   What's contributing to your limits usage?
   Approximate, based on local sessions on this machine — does not include other devices or claude.ai
   
   Last 24h · these are independent characteristics of your usage, not a breakdown
   
   100% of your usage came from subagent-heavy sessions
    Each subagent runs its own requests. Be deliberate about spawning them — and 
    consider configuring a cheaper model for simpler subagents.
   
   35% of your usage was at >150k context
    Longer sessions are more expensive even when cached. /compact mid-task, /clear 
    when switching to new tasks.
   
   Subagents               % of usage
   general-purpose                 8%
   
   d to day · w to week

   Esc to cancel

```

### 8/14/2026

Started writing about using Claude 20 hours ago. When I thought I had used up a $50 plan. I thought it was $100 but it was $50 and I added another $50 but even after adding another $50 I couldn't do more and I'm very confused by that. The billing model for Claude Code is insanely confusing. You have some kind of limit but it's not your full budget but you run out of tokens or credits or whatever it is they track. It said I could pay for usage credits and I said Ok but it never worked so I gave up.

I was able to work again today but then ran out of tokens/credits again in a few hours. I was using ultramode to get through a few bugs and I think it did actually help resovle an issue so fine. 

But how many tokens or credits or dollars have I acutally used? So I'm looking in my account and I have two invoices for 6/29 and 7/29 and I don't understand that at all. Where did my $100 I added go? What is going on here?

Wait what. I was logged in and under billing I saw:

June 28 - $50
July 28 - $50

I was sure I added another $100 somewhere. 

I logged in under my primary email thinking maybe that was it. Nothing. I have no account there.

I logged out and logged back in and was having some problems getting into my account. It didn't fully log me out of my primary email account. I finally switched from Claude.ai ot the platform link.

And now I see:

June 30 - $20
August 13 - $100

What??? 

And in this plan I see 0% used with a $1000 monthly spend limit? Oh. This says something about API key. Was I using the other account just now?

Sorry bu this is too dang confusing. Maybe I'll try to use the API key tomorrow if I can't use the browser login. My understanding is that the API key option is more expensive. How do I tell which one I've used?

Ah, there it is. I now can head over to Claude.ai with my login and there I see the two $50 charges. Hmm. Ok.

Well mystery solved and time for bed anyway.

### Costs while building an AI Agent Bootstrap Script and Framework
**Timeline:** Mar 7, 2026 - Aug 5, 2026

| Service / Cost Item | Total | Mar 2026 | Apr 2026 | May 2026 | Jun 2026 | Jul 2026 | Aug 2026* |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Total costs** | **$3,824.49** | **$387.45** | **$427.51** | **$657.93** | **$786.01** | **$1,488.85** | **$76.75** |
| Kiro | $2,290.80 | $193.55 | $129.07 | $285.79 | $457.71 | $1,192.42 | $32.26 |
| Virtual Private Cloud | $468.62 | $53.44 | $121.94 | $141.30 | $107.82 | $36.78 | $7.36 |
| Elastic Compute Cloud - Compute | $375.41 | $39.45 | $44.28 | $100.12 | $96.80 | $85.21 | $9.54 |
| EC2 - Other | $270.34 | $43.20 | $54.37 | $56.12 | $54.54 | $55.39 | $6.72 |
| Key Management Service | $188.80 | $24.61 | $28.95 | $33.12 | $41.56 | $52.83 | $7.72 |
| Route 53 | $64.06 | $0.60 | $12.85 | $13.09 | $13.29 | $13.71 | $10.53 |
| Registrar | $58.00 | $15.00 | $15.00 | $8.00 | - | $20.00 | - |
| Secrets Manager | $25.58 | $7.06 | $7.80 | $6.08 | $2.29 | $2.07 | $0.28 |
| GuardDuty | $23.87 | $3.67 | $5.19 | $5.68 | $3.25 | $5.57 | $0.50 |
| Security Hub | $23.86 | $1.00 | $1.20 | $1.20 | $1.75 | $17.60 | $1.10 |
| Simple Storage Service | $22.12 | $3.59 | $4.71 | $4.67 | $4.56 | $4.20 | $0.39 |
| CloudWatch | $5.63 | $1.49 | $1.00 | $1.00 | $1.00 | $1.00 | $0.14 |
| Budgets | $1.39 | $0.25 | $0.30 | $0.31 | $0.30 | $0.23 | - |
| Relational Database Service | $1.29 | $0.23 | $0.28 | $0.29 | $0.28 | $0.21 | - |
| Inspector | $1.08 | $0.00 | $0.00 | $0.00 | $0.38 | $0.62 | $0.09 |
| CloudFront | $0.91 | $0.16 | $0.18 | $0.14 | $0.15 | $0.23 | $0.05 |
| EC2 Container Registry (ECR) | $0.66 | $0.08 | $0.17 | $0.18 | $0.11 | $0.10 | $0.01 |
| Config | $0.60 | - | - | $0.60 | - | - | - |
| CloudTrail | $0.46 | $0.00 | $0.11 | $0.11 | $0.11 | $0.11 | $0.02 |
| Macie | $0.43 | - | - | $0.00 | $0.02 | $0.36 | $0.05 |
| Systems Manager | $0.33 | $0.04 | $0.09 | $0.10 | $0.07 | $0.03 | - |
| Tax | $0.13 | $0.00 | $0.00 | $0.00 | - | $0.13 | $0.00 |
| Detective | $0.12 | $0.02 | $0.02 | $0.03 | $0.03 | $0.02 | - |
| Amplify | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| CloudShell | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | - |
| Glue | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Lambda | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | - | - |
| DynamoDB | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | - |
| Simple Notification Service | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Simple Queue Service | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Certificate Manager | $0.00 | - | $0.00 | $0.00 | - | $0.00 | - |
| API Gateway | $0.00 | - | $0.00 | $0.00 | - | - | - |
| Payment Cryptography | $0.00 | - | - | - | $0.00 | - | - |

*\*Month ongoing / incomplete data.*


**Date:** July 2, 2026

TIL after analyzing my costs what is really going on with some of the cost metrics and why I thought I had been billed for a full $200 plan when I couldn't use a single credit. When you log in and look at the cost dashboard, if you have signed up for a $200 plan, it shows you a $200 charge immediately. Blam. Then you look at your forecasted costs and it may be less than $200. Wat. Somehow if I cancel the plan mid-month I'm not charged the full $200 but that charge doesn't adjust to actual. It's all very confusing. All I know is that whether I am billed the full $200 or not I still haven't gotten this porject done and I'm burning a lot of tokens. Yesterday a new model was released and every time that happens the existing models go haywire. And I'm not sure it can be just racked up to system overload. If you know what noops are good for...I keep reporting this mantra that you need to track eveyrhing and we need to pinpoint and fully understand what is causing that to happen. It is a risk in more ways than one for businesses and potentially national security. 

**** We need to be able to understsand this stuff better to fix it. ****

I can't see inside the systems so I can't fully tell from the outside what is going on. I can only measure what I can see and the the data I can access.

**Date Range:** July 1 - 2, 2026

Used up a full Kiro $200 plan in two days. New models were released and the agents are really spinnning their wheels again. I noticed an interesting graph but apparently it onlys shows metrics for inactive subscriptions. This shows credits burned in the last couple of days mostly trying to fix issues with requirements and bugs. (i.e. no real progress made just trying to get things working I thought were working before.) I really think something is going on whenever new Anthropic models are release in AWS or on Anthropic or both. I'm going to try to track this better but as you can see burned way more tokens per day than before and I'm just trying to get something DONE. I mean really DONE.

<img width="1308" height="561" alt="credit-usage" src="https://github.com/user-attachments/assets/7a4e5dad-c9cb-4f6d-b679-87971cbc6e2d" />

**Date Range:** Mar 7, 2026 - Jul 2, 2026

| Service / Resource | Total | Mar 2026 | Apr 2026 | May 2026 | Jun 2026 | Jul 2026* |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Total costs** | **\$2,151.92** | **\$359.07** | **\$387.55** | **\$621.52** | **\$755.02** | **\$28.76** |
| Kiro | \$1,079.02 | \$193.55 | \$129.07 | \$285.79 | \$457.71 | \$12.90 |
| Virtual Private Cloud | \$411.17 | \$50.07 | \$118.34 | \$137.58 | \$104.22 | \$0.97 |
| Elastic Compute Cloud - Compute | \$283.88 | \$39.45 | \$44.28 | \$100.12 | \$96.80 | \$3.23 |
| EC2 - Other | \$169.65 | \$34.04 | \$43.09 | \$45.92 | \$45.85 | \$0.75 |
| Key Management Service | \$106.68 | \$19.79 | \$22.96 | \$27.15 | \$35.57 | \$1.20 |
| Registrar | \$38.00 | \$15.00 | \$15.00 | \$8.00 | \$0.00 | \$0.00 |
| Route 53 | \$31.97 | \$0.60 | \$7.35 | \$7.59 | \$7.79 | \$8.64 |
| GuardDuty | \$14.07 | \$2.81 | \$4.19 | \$4.66 | \$2.23 | \$0.18 |
| Secrets Manager | \$8.05 | \$1.90 | \$1.40 | \$2.38 | \$2.29 | \$0.08 |
| CloudWatch | \$4.53 | \$1.49 | \$1.00 | \$1.00 | \$1.00 | \$0.04 |
| Security Hub | \$2.15 | \$0.20 | \$0.24 | \$0.21 | \$0.79 | \$0.71 |
| Simple Storage Service | \$0.84 | \$0.09 | \$0.34 | \$0.24 | \$0.17 | \$0.01 |
| Config | \$0.60 | \$0.00 | \$0.00 | \$0.60 | \$0.00 | \$0.00 |
| EC2 Container Registry (ECR) | \$0.55 | \$0.08 | \$0.17 | \$0.18 | \$0.11 | \$0.00 |
| Inspector | \$0.40 | \$0.00 | \$0.00 | \$0.00 | \$0.38 | \$0.02 |
| CloudTrail | \$0.33 | \$0.00 | \$0.11 | \$0.11 | \$0.11 | \$0.00 |
| Macie | \$0.03 | \$0.00 | \$0.00 | \$0.00 | \$0.02 | \$0.01 |

**Date Range:** Jun 1, 2026 - Jun 12, 2026

What is interesting here is that on the main readme I tracked cost per day and the cost per day is dramatically rising. Not sure if I'm really using it that much more. I have been working long hours all month. Seems like the cost is just going up. Also for each $200/month plan I started and canceled was not actually billed the full $200. Not sure if I'm going to get hit at the end of the month.

### Costs while building an AI Agent Bootstrap Script and Framework
**Date Range:** Mar 7, 2026 - Jun 28, 2026

| Service / Category | Total | Mar 2026 | Apr 2026 | May 2026 | Jun 2026* |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Total costs** | **$2,042.40** | **$359.07** | **$387.55** | **$621.52** | **$674.26** |
| Kiro | $1,012.57 | $193.55 | $129.07 | $285.79 | $404.16 |
| Virtual Private Cloud | $405.07 | $50.07 | $118.34 | $137.58 | $99.09 |
| Elastic Compute Cloud - Compute | $269.50 | $39.45 | $44.28 | $100.12 | $85.65 |
| EC2 - Other | $163.63 | $34.04 | $43.09 | $45.92 | $40.58 |
| Key Management Service | $101.40 | $19.79 | $22.96 | $27.15 | $31.49 |
| Registrar | $38.00 | $15.00 | $15.00 | $8.00 | $0.00 |
| Route 53 | $23.23 | $0.60 | $7.35 | $7.59 | $7.70 |
| GuardDuty | $13.50 | $2.81 | $4.19 | $4.66 | $1.84 |
| Secrets Manager | $7.69 | $1.90 | $1.40 | $2.38 | $2.02 |
| CloudWatch | $4.38 | $1.49 | $1.00 | $1.00 | $0.89 |
| Security Hub | $0.85 | $0.20 | $0.24 | $0.21 | $0.20 |
| Simple Storage Service | $0.82 | $0.09 | $0.34 | $0.24 | $0.15 |
| Config | $0.60 | $0.00 | $0.00 | $0.60 | $0.00 |
| EC2 Container Registry (ECR) | $0.53 | $0.08 | $0.17 | $0.18 | $0.10 |
| CloudTrail | $0.32 | $0.00 | $0.11 | $0.11 | $0.10 |
| Inspector | $0.31 | $0.00 | $0.00 | $0.00 | $0.31 |

**Date Range:** Mar 7, 2026 - Jun 12, 2026

This is interesting because I had a $200 plan which was all used up by June 10th so I cancelled it and started a new one. But this report is not reflecting that dollar amount. The total cost is < $200. Hmm. Also, my EC2 costs are higher than they should be for reasons...it's not you, it's me. VPC endpoints. WHY????

| Service / Category | Total | Mar 2026 | Apr 2026 | May 2026 | Jun 2026* |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Total costs** | **$1,571.19** | **$359.07** | **$387.55** | **$621.52** | **$203.04** |
| Kiro | $692.19 | $193.55 | $129.07 | $285.79 | $83.77 |
| Virtual Private Cloud | $344.92 | $50.07 | $118.34 | $137.58 | $38.94 |
| Elastic Compute Cloud - Compute | $222.59 | $39.45 | $44.28 | $100.12 | $38.74 |
| EC2 - Other | $141.06 | $34.04 | $43.09 | $45.92 | $18.01 |
| Key Management Service | $83.94 | $19.79 | $22.96 | $27.15 | $14.03 |
| Registrar | $38.00 | $15.00 | $15.00 | $8.00 | $0.00 |
| Route 53 | $22.93 | $0.60 | $7.35 | $7.59 | $7.39 |
| GuardDuty | $12.35 | $2.81 | $4.19 | $4.66 | $0.69 |
| Secrets Manager | $6.52 | $1.90 | $1.40 | $2.38 | $0.84 |
| CloudWatch | $3.89 | $1.49 | $1.00 | $1.00 | $0.40 |
| Simple Storage Service | $0.74 | $0.09 | $0.34 | $0.24 | $0.07 |
| Security Hub | $0.70 | $0.20 | $0.24 | $0.21 | $0.05 |
| Config | $0.60 | $0.00 | $0.00 | $0.60 | $0.00 |
| EC2 Container Registry (ECR) | $0.48 | $0.08 | $0.17 | $0.18 | $0.04 |
| CloudTrail | $0.26 | $0.00 | $0.11 | $0.11 | $0.04 |
| Inspector | $0.02 | $0.00 | $0.00 | $0.00 | $0.02 |
| Amplify | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| CloudShell | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Glue | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Lambda | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Simple Notification Service | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Simple Queue Service | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Tax | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Certificate Manager | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| API Gateway | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| DynamoDB | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Macie | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |
| Payment Cryptography | $0.00 | $0.00 | $0.00 | $0.00 | $0.00 |

__________

**Date Range:** Mar 7, 2026 - Jun 2, 2026


| Cost Category | Total | Mar 2026 | Apr 2026 | May 2026 | Jun 2026* |
| :--- | ---: | ---: | ---: | ---: | ---: |
| **TOTAL COSTS** | **\$1,389.34** | **\$359.07** | **\$387.55** | **\$621.52** | **\$21.20** |
| Kiro | \$613.43 | \$193.55 | \$129.07 | \$285.79 | \$5.02 |
| Virtual Private Cloud | \$306.23 | \$50.07 | \$118.34 | \$137.58 | \$0.24 |
| Elastic Compute Cloud - Compute | \$190.31 | \$39.45 | \$44.28 | \$100.12 | \$6.45 |
| EC2 - Other | \$125.75 | \$34.04 | \$43.09 | \$45.92 | \$2.70 |
| Key Management Service | \$71.93 | \$19.79 | \$22.96 | \$27.15 | \$2.02 |
| Registrar | \$38.00 | \$15.00 | \$15.00 | \$8.00 | \$0.00 |
| Route 53 | \$20.09 | \$0.60 | \$7.35 | \$7.59 | \$4.55 |
| GuardDuty | \$11.69 | \$2.81 | \$4.19 | \$4.66 | \$0.03 |
| Secrets Manager | \$5.75 | \$1.90 | \$1.40 | \$2.38 | \$0.08 |
| CloudWatch | \$3.56 | \$1.49 | \$1.00 | \$1.00 | \$0.07 |
| Simple Storage Service | \$0.68 | \$0.09 | \$0.34 | \$0.24 | \$0.01 |
| Security Hub | \$0.66 | \$0.20 | \$0.24 | \$0.21 | \$0.01 |
| Config | \$0.60 | \$0.00 | \$0.00 | \$0.60 | \$0.00 |
| EC2 Container Registry (ECR) | \$0.44 | \$0.08 | \$0.17 | \$0.18 | \$0.01 |
| CloudTrail | \$0.22 | \$0.00 | \$0.11 | \$0.11 | \$0.00 |
| Amplify | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| CloudShell | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Glue | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Lambda | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Inspector | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Simple Notification Service | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Simple Queue Service | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Tax | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Certificate Manager | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| API Gateway | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| DynamoDB | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |
| Macie | \$0.00 | \$0.00 | \$0.00 | \$0.00 | \$0.00 |

