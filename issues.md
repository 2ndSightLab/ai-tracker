
# Issues

Fixed issues in fixed.md

## Issues

🟡 SSH key

🟡 KMS key policies not allowing whole env

🟡 Secrets key not restricted to secrets manager

🟡 Open up SCP to SSM get param to use this:

aws ssm get-parameters --names /aws/service/ami-amazon-linux-latest/al2023-ami-kernel-default-x86_64 --query "Parameters[0].Value" --text --profile work-test-ami-oadmi

🟡 Ec2 Instances

🟡 AMIs

🟡 Ami share to OU

🟡 Added ECR not right - maybe deploying with wrong role
