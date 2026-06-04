
# Issues

Fixed issues in fixed.md

🟡 May be a dup but I think the user/role has to be deployed prior to teh location it is in the base env.

🟡 Rename and account - name, email, alias - use this before closing an account

🟡 Close account is not working and before closing an account need to fix the following: change alias name, change account name, change email address - to avoid conflicts if need to recreate the account.

🟡 The KMS key polic is too broad - allows access to any key and is applying it to eevery lamda in ou. I have an SCP to block that but still annoying. I need to review all the policies in detail later and will use the IAM access analyzer plus manual review. I don't think IAM access analyzer handles resource policies but prowler will to a degree.
