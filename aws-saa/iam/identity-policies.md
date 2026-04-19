+++
tags = ['aws', 'permissions']
+++

# Identity Policies

A type of policy that get attached to identities in aws. They either grant or
deny access to aws resources.


**Types of Identities**:

1. IAM [[users]]
2. IAM Groups
3. IAM Roles

## Policy Document

Usually written in json, and at a high level a policy document is just 1+
statements that describe what actions can and can't be performed on a given
resource.

**Example**:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "FullAccess",
            "Effect": "Allow",
            "Action": ["s3:*"],
            "Resource": ["*"]
        },
        {
            "Sid": "DenyCatBucket",
            "Action": ["s3:*"],
            "Effect": "Deny",
            "Resource": ["arn:aws:s3::::catgifs", "arn:aws:s3::::catgifs/*"]
        }
    ]
}
```

### Statement

A statement has the following fields:

- `Sid`: lets you identify a statement and what it does (optional)  
- `Effect`: Allow | Deny, based on if there is a match on action and resource
  based on what the IAM identity is doing
- `Action`: list of actions to match to, wild cards are allowed in here
- `Resource`: list of aws resources to match to, wild cards are allowed in here
  but it is advised to use the Amazon Resource Name (ARN)

In case there is a collision of permission overlap then it follows the following
priority:

1. Explicit deny
2. Explicit allow
3. Default deny (implicit)

Note: the most restrictive permission takes priority.

Same priority takes place when there are multiple policies at play. For instance
when a user has multiple policies, let it be an explicit policy, group, or role,
as well as a resource policy then aws will take all the policies as evaluate
them as single one. With the same rule of having the most restrictive
permission win and if there is no explicit permission then deny by default.

## Types of Policies

1. **Inline Policy**: policy applied individually to a user, with each being their
own policy with no relation to each other. Usually used for *exceptions*

2. **Managed Policy**: created as their own object, and then assigned to
identities that need to use that policy. This way they are reusable and point to
the same object making them *reusable and low management*
