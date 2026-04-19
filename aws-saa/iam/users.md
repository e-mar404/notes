+++
tags = ['iam', 'global-service']
+++

# Users

IAM Users are identities used for anything requiring **long term** aws access.
For instance people, applications or service accounts.

## Authorization vs Authentication Process

1. the process starts with a **principal**, which is an unauthenticated identity
   trying to prove who they are to aws, either through username/password or 
   through API keys
2. the principal will go through **authentication** and if that succeeds then it
   will turn into an **authenticated identity**
3. once an authenticated identity aws knows what policies apply to that identity
   and will allow/deny actions the identity takes through **authorization**

## Limitations

1. You are only allowed **5000** iam users **per account**. Since this is a global
service then all user accounts count towards this limit and is not per region.
2. iam users can be a member of a max of **10** groups

These limitations are matter when any of the following apply:

- building internet scale applications
- large organization with 5000+ employees
- organization mergers that bring in other users that were not accounted during
  initial design 

In order to get over this you can use IAM roles and identity federation.
