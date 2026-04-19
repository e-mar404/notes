+++
tags = ['iam']
+++

# IAM Groups

Simply put are just containers for [[users]], groups are **not** able to log in and
do not have any credentials. 

Note: Important for the exam, since it might have a trick question with an 
answer saying to log in to a group.

Purposes of groups:

- ability to organize users into common groups or responsibilities
- groups are able to have iam [[identity-policies]] attached to them, and
  supports both inline and managed policies

## Limitations

1. Any given [[users]] can only be a part of 10 groups, but there is no limit to
   how many users are in a specific group (excluding the [[users#Limitations]] 
   of 5000 users per account)
2. there is a soft limit of 300 groups per account, but can be increased with a
   support call
3. there can be no group **nesting**, so no group can be a part of another group
4. groups are not a **true identity**, they cannot be referenced as a principal
   in a policy
