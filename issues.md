
# Issues

Fixed issues in fixed.md

🟡 As per usual it messed up the DNS. It was only supposed to copy records except NS records and it update the NS records so I told it to fix that and fix and validate any incorret records at the time of the move.

🟡 Move hosted zone didn't update existing hosted zone so now the correct NS records are in one acount and the domain is associated ot the one with the wrong NS records I think not sure what is going on figure out tomororw.

🟡 Need a way to handle dup hostd zones in account 

🟡 Delete hosted zone didn't work becuase need to delete child records first.

🟡 Ram sharing worked for one VPC but it's not working for the other three nad the models are going aroudn and around in circles and cannot figure it out.

🟡 May be a dup but I think the user/role has to be deployed prior to teh location it is in the base env.

🟡 Rename and account - name, email, alias - use this before closing an account

🟡 Close account is not working and before closing an account need to fix the following: change alias name, change account name, change email address - to avoid conflicts if need to recreate the account.

🟡 The KMS key polic is too broad - allows access to any key and is applying it to eevery lamda in ou. I have an SCP to block that but still annoying. I need to review all the policies in detail later and will use the IAM access analyzer plus manual review. I don't think IAM access analyzer handles resource policies but prowler will to a degree.

🟡 Deploy resources concurrently where possible; my initial attempt to ask this quetion got really convoluted sugestions.
