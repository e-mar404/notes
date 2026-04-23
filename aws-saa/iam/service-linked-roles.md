+++
tags = ['iam', 'permissions']
+++

# Service Linked Roles

These are very similar to iam [[roles]]. But the difference is that its a
specific role linked to a specific *aws service*. They are predefined by a 
service providing permissions that a service needs to interact with other aws
services on your behalf.

If, during set up, the service doesn't have a role assigned already then it will
create it or ask you to create it during set up, or even within [[iam]].

A very important difference between service linked roles and regular [[roles]]
is that service linked roles cannot be deleted unless they are not being used by
any service.

## Role Separation

This is the ability to separate the role usage and the identity that assigns
them.

For instance, having a user assign a role to a service while not having that
role assigned to the user. 

This means that the user can pass a role to a service that contains more
permissions than the user creating the service has, one of those could be the
permission of creating roles them selves.

In order to do this permissions for `"iam:ListRoles"` & `"iam:PassRole"` actions on
the role resource are needed in an [[identity-policies]].
