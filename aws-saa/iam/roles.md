+++
tags = ['iam', 'missing-notes']
+++

# Roles

## IAM Roles - The Tech

How are roles different to users?

Roles, unlike [[groups]], are still true identities that can be used to 
authenticate against aws. And unlike [[users]], which are used when there is 1
clearly identifiable principal, roles are used whenever you cant clearly put a
number of identities that will assume an aws identity, if the identities are
external or if that number is >5000. 

Identities temporarily get a role assigned to them and based on the permissions
that are attached to the role then they are able to create temporary credentials
used to authenticate with aws.

## Identity Policies

Roles have 2 types of [[identity-policies]]:

- Trust policies
- Permission policies

### Trust Policy

This lets aws know what external identities are able to assume the role that
they are trying to get. This can be web credentials, mobile applications, aws
services, or other identity provider accounts.

### Permission Policy

This policy tells aws what actions can be performed on what resources, very
similar to how [[identity-policies]] work on [[users]] with both inline and
managed policies being able to be used for roles.

## Security Token Service (STS)

STS gives the roles a temporary credential to use while they are accessing aws
resources. Usually they last 1hr for federated users, and 12hrs for roles. This
can be user configured to last between 15min and 12hrs.


---
## When to use IAM Roles
Give 4 examples of when to use roles.
Why is it not recommended to hard code credentials?
What relationship is there between external identities and aws resources?
What is ID Federation?
What benefit do web identities bring to roles and aws access?
