
# Issues

Fixed issues in fixed.md

## Issues

🟡 Delete invalid entries in the XML validator - user has option to delete after reviewing

🟡 Force redeploy a specific node (one that is green)

🟡 Dependency validator that flags dependency errors based on AWS dependency file

🟡 Open up SCP to SSM get param to use this:

aws ssm get-parameters --names /aws/service/ami-amazon-linux-latest/al2023-ami-kernel-default-x86_64 --query "Parameters[0].Value" --text --profile work-test-ami-oadmi

🟡 Ami share to OU

🟡 Don't query acconts if tracker is green 

🟡 Skip the whole env if the tracker is green
