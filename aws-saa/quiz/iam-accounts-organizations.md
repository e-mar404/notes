+++
tags = [ 'aws-account', 'iam', 'organizations' ] 
+++

# IAM & Orgs Quiz

1. Is there a limit to the number of IAM users in an [[aws-account]]? If so, how
many?

    a) No limit
    b) 1000 per region
    c) 3000 per account
    d) 5000 per account
    e) 5000 per region

A: d

2. Which of the following are features of iam [[groups]]?

    a) admin groupings of IAM users
    b) can hold identity permissions
    c) can be used to login (access keys)
    d) can eb used to login (user/pass)
    e) can be nested

A: a, b

3. Within aws [[identity-policies]], what is always a priority?

    a) explicit allow
    b) explicit deny
    c) depends on the order in the policy
    d) no priority

A: b

4. what two policies are assigned to a iam [[roles]]?
    
    a) permissions policy
    b) assumption policy
    c) resource policy
    d) trust policy

A: a, d

5. Which of the following are true for iam [[roles]]?

    a) Roles have associated Long Term Credentials (Access Keys)
    b) Roles can be assumed
    c) When assumed - temporary credentials are generated
    d) Roles can be logged into
    e) When an identity logs into a role - temporary credentials are generated

A: b, c

6. What 3 features are provided by aws [[organizations]]?

    a) Consolidated billing
    b) Managed assistance for company and AWS account mergers
    c) AWS Account restrictions using SCP
    d) Account organization via OU's
    e) Protection against credential leaks
    f) Company ID reports

A: a, c, d

7. What functionality is provided by [[cloudtrail]]?

    a) log ingestion
    b) metrics management
    c) account restrictions
    d) account wide auditing and api logging

A: d

8. Is is possible to restrict what the account root user can do?

    a) Always
    b) Never
    c) If AWS Organisations are used
    d) If AWS Organizations are used .. but not the management account

A: d

9. What is [[organizations#Role Switching]]?

    a) Changing the permissions on an IAM Role
    b) Changing the TRUST on a Role
    c) Changing who can assume a Role
    d) Logging into a Role
    e) Assuming a role in another AWS account to access that account via the console UI

A: e

10. What are valid IAM [[identity-policies#Types of Policies]]?

    a) AWS Managed Policy
    b) Customer Managed Policy
    c) Self-Managed Policy
    d) Inline Policies
    e) External Policies

A: a, b, d
