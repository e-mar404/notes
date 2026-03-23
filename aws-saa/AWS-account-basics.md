# AWS Accounts - The basics

Anki QA:

An AWS account is ... a container for identities (users) and resources

AWS accounts require a unique email address and card (T/F) ... true

By default AWS account root users are able to access other AWS accounts (T/F) ...
false

AWS root user can be restricted (T/F) ... false

IAM stands for ... Identity and Access Management

A pro for the boundary of an AWS account is ... that all impact of admin errors,
bad actors or exploits are contained to only what that account can access. 

## IAM Basics

Least Privilege Access ... only give minimum permissions for a user or account to
perform what is needed

IAM is: A. Globally Resilient B. Regional Resilient C. AZ Resilient ... A.
Globally Resilient

What are the 3 main things that IAM creates ... Users, Groups, Roles

In IAM, Users are ... Identities which represent humans or applications that
need access to the AWS account resources

In IAM, Groups are ... A collection of related users

In IAM, Roles are ... Used by AWS services or are granted to external access to
the AWS account. Used when the number of grants are uncertain

In IAM, Policies are ... Rules for what services are able to be accessed or not,
only when attached to users, groups, or roles

The main roles of IAM are ... Managing identities (IDP), Authentication (prove
you are who you claim to be), Authorization (allow or deny access to resources)

When would you use IAM AccessKeys instead of username/password ... You can have
2 access keys per user, access keys are usually used for CLIs and
applications, you can disable and enable access keys while the user is still
active
