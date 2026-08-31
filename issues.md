
# Issues

Fixed issues in fixed.md

## Issues

🟡 AWS type depedencies configuration

🟡 Org config id dependencies configuration

🟡 Dependency validator that flags dependency errors based on AWS dependency file

🟡 Change dependency file in deployer to point to org dependencies

🟡 Add individual network resources with correct types.
   - need vpc, etc. in ami account to complete ami deployment

🟡 Open up SCP to SSM get param to use this:

aws ssm get-parameters --names /aws/service/ami-amazon-linux-latest/al2023-ami-kernel-default-x86_64 --query "Parameters[0].Value" --text --profile work-test-ami-oadmi

🟡 Ec2 Instances to create amis

🟡 AMIs

🟡 Ami share to OU
