+++
tags = []
+++

# Service Control Policies

SCPs are documents (usually json) that limit aws accounts in an organization.
They can go on on the following objects:

- [[organizations#Member]] accounts
- the root of the [[organizations]]
- any organizational unit in [[organizations]]

While a [[organizations#Management]] account can have an SCP attached to it, it
will not be limited in any way.

## Limiting Accounts

While SCPs limit accounts they are not for granting permissions. They only limit
what the [[aws-account]] is able to do. Which interestingly enough is the only
way to limit the root account. By applying an SCP to the account itself. In
reality the root account still can access everything that the account has access 
to, it is just that the account has access to less things.

## Allow vs Deny Lists

There are 2 ways that SCPs can limit an [[aws-account]]. 

### Deny List

One is by having every service and action allowed by default and then just add
**deny lists** to deny services and actions. This option is a lot more flexible
and has a lot more leeway, specially since it will allow new services that come
out by default. This potentially brings in less overhead at the cost of risk.

### Allow List

The second way is to have everything denied by default and then just add **allow
lists** to allow specific services and actions. This is a lot more restrictive
and can have more overhead. But it might be needed if strict boundaries are
required.

## Overlap Between Identity Policies 

While there is some similarity between SCPs and [[identity-policies]] they are 2
completely different documents. [[identity-policies]] manage permissions, and as
discussed before, SCPs do not grant permissions in the same sense.

**Example**

Even if the [[identity-policies]] gives an identity permissions for action A, B
C; if there is an SCP that limits the account to actions B, C, D, then the
identity will only be able to access B & C.
