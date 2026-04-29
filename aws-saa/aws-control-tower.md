+++
tags = ['aws-accounts' ]
+++

# Control Tower

Control Tower is a service that makes it easy to manage multiple account by
orchestrating the creation and management of them.

This is similar but not the same to [[organizations]], this Control Tower there
is a lot more automated management of the accounts. It utilizes CloudFormation a
lot to accomplish this so it will not be surprising if stacks get created. 

## Landing Zone
    
The landing zone can be thought of as a container for Control Tower. This holds
the accounts created through Control Tower. It is also possible to start using
Control Tower while already having a existing [[organizations]] and
organizational units. Control Tower will leave those unchanged and only manage
the accounts that it creates.

A huge pro for using this is that [[iam]] SSO is very easy to integrate for the
multi-account environment.

By default the landing zone will create 2 OUs for account management:

### Security OU

On the security ou 2 accounts get created, one for **Audit** and another for **Log
Archive**
    
### Sandbox OU

## Guard Rails

Control Tower also provides ways to allow/deny accounts from doing different
things. 

There are 3 different "priorities" of a guard rail:

1. Mandatory
2. Strongly recommended
3. Elective

Guard rails have 2 very clear roles, they can either be **preventative** and
stop actions from happening or **detective** and just identify overstepping 
actions.

The guard rails will have different statuses depending on their compliance:
clear, in violation, not enabled.

## Account Factory

This is how multiple [[aws-account]]s get created in an automated way. The way
and process of providing the generated accounts is heavily influenced by the use
case, but in general it can follow the SDLC of accounts and software.
