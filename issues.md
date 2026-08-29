
# Issues

Fixed issues in fixed.md

## Issues

🟡 Disable telemetry in Claude by default:

 {
     {
        "model": "opus[1m]",
         "effortLevel": "high",
         "theme": "dark",                                                                                                  
         "feedbackSurveyRate": 0,                                                                                          
         "env": {                                                                                                          
           "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1",                                                                
           "DISABLE_TELEMETRY": "1",                                                                                       
           "DISABLE_ERROR_REPORTING": "1",                                                                                 
          "CLAUDE_CODE_ENABLE_TELEMETRY": "0",                                                                            
          "DISABLE_NON_ESSENTIAL_MODEL_CALLS": "1",                                                                       
          "DISABLE_BUG_COMMAND": "1",                                                                                     
          "DISABLE_AUTOUPDATER": "1"                                                                                      
      }                                                                                                                 
}

the telemetry flags live in ~/.claude/settings.json env

🟡 Open up SCP to SSM get param to use this:

aws ssm get-parameters --names /aws/service/ami-amazon-linux-latest/al2023-ami-kernel-default-x86_64 --query "Parameters[0].Value" --:^) ut text --profile work-test-ami-oadmi

🟡 Ec2 Instances

🟡 AMIs

🟡 Ami share to OU

🟡 New account not deploying due to stopping other accounts on error - resolve manually.

🟡 Added ECR not right - maybe deploying with wrong role

🟡 All ec2 error handling






