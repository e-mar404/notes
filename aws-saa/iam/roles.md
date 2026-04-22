+++
tags = ['iam', 'missing-notes']
+++

# Roles

## IAM Roles - The Tech

Roles, unlike [[groups]], are still true identities that can be used to 
authenticate against aws. And unlike [[users]], which are used when there is 1
clearly identifiable principal, roles are used whenever you cant clearly put a
number of identities that will assume an aws identity, if the identities are
external or if that number is >5000. 

> IAM roles are *assumed* .. *you become* that role

Identities temporarily get a role assigned to them and based on the permissions
that are attached to the role then they are able to create temporary credentials
used to authenticate with aws.

### Identity Policies

Roles have 2 types of [[identity-policies]]:

- Trust policies
- Permission policies

Also just like how users are able to be referenced by resource policies, also
can roles. This is because roles are true identities.

#### Trust Policy

This lets aws know what identities are able to assume the role that they are
trying to get. This can be web credentials, mobile applications, aws services,
or other identity provider accounts.

#### Permission Policy

This policy tells aws what actions can be performed on what resources, very
similar to how [[identity-policies]] work on [[users]] with both inline and
managed policies being able to be used for roles.

### Security Token Service (STS)

STS gives the roles a temporary credential to use while they are accessing aws
resources. Usually they last 1hr for federated users, and 12hrs for roles. This
can be user configured to last between 15min and 12hrs.

Whenever the *temporary security credentials* expire the identity will have to
re-assume the role and get new credentials generated.

If the [[#permission-policy]] changes then also will the permissions of the
temporary security credentials.

## When to use IAM Roles

1. **For aws services themselves**

For instance, instead of hard coding credentials (not secure btw) for a lambda
function to use. Have the lambda assume the role needed and use the temp
credentials to do what it needs to do.

There might be an unknown number of instances running at any given point and
that is one of the reasons on why to use roles over [[users]]. An unidentifiable
number of principals.

2. **For emergency situations**

There might be a base level of permissions that a user might need. They might
only need read only access to services, but in any emergency situation where the
user does need to perform an action they are able to assume a role.

This way the role is able to be used as a "break glass in case of..." resource.

3. **When using existing, external, identities**

For instance, whenever you are bringing in an on-premises active directory then
you can use roles to have those external identities authenticate against aws.

This is not just necessary because of the [[users#Limitations]], but also
because aws cannot authenticate against external accounts by default, you need
to set up a different auth flow.

4. **Designing a mobile app**

Usually mobile apps have millions of users, and instead of creating an aws user
for every one then the mobile devs are able to use identity federation to assign
a role to their account to be able to access aws resources.

This scales to millions of users and does not run into [[users#Limitations]]

5. **Cross account access**

Whenever you're interacting with another aws account, instead of creating a new
users for each other to be able to access resources on the external aws account
you can setup roles.
