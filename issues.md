
# Issues

Fixed issues in fixed.md

## Issues

🟡 Just realized need depedendency types at ORG level.
   - copy dependenty file from default org
   - add aility to edit it
   - deploy project needs to use it
   - make sure dep on resource ids not types

🟡 Add individual network resources with correct types.
   - need vpc, etc. in ami account to complete ami deployment

🟡 Open up SCP to SSM get param to use this:

aws ssm get-parameters --names /aws/service/ami-amazon-linux-latest/al2023-ami-kernel-default-x86_64 --query "Parameters[0].Value" --text --profile work-test-ami-oadmi

🟡 Ec2 Instances to create amis

🟡 AMIs

🟡 Ami share to OU
