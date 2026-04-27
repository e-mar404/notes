+++
tags = ['iam', 'aws-account']
+++

# Organizations

Organizations are used to make managing multiple [[aws-account]] a lot easier.
Once you get into enterprise and bigger company settings, where they can have
100+ accounts it get very tedious to handle them.

## Types of AWS Account

### Standard

In terms of aws organizations an [[aws-account]] that is not part of an
organization is called a **standard aws account**.

### Management

When creating an aws org, the [[aws-account]] changes from being a standard
account to a **management aws account**. In the past these used to be called
*master* accounts, or in terms of [[#billing]] it is called the payment account.

The organization is **not** created **inside** the management account, it is
just used to start the org.

### Member

Any other account in an organization that is not the [[#Management]] account is
considered a **member aws account**.

There can be 0+ member accounts inside an organization.

## Adding Accounts 

There are 2 ways of adding an account to the org:

1. by inviting an existing [[#Standard]] account, which they accept the invite
to join the org
2. by creating a new account through the [[#Management]] account, which will get
automatically joined to the org

## Structure

The structure of the organization is hierarchical, in the form of an inverted
tree. With the top level being the **organization root**. This is not the same
as root accounts on an [[aws-account]]. This is just a container that can have
1+ [[#Member]] or [[#Management]] accounts.

Other than accounts the organization root can contain other containers, called
**organizational unit**. This lets you have a nested structure to modify
depending to the business needs.

## Billing

One of the biggest advantages of using an organization is the benefit of
**consolidated billing**. This enables the [[#Member]] accounts to not worry
about billing since the [[#Management]] will be the one that handles that. 

Consolidated billing will take off a huge management burden of multiple account
billing and can pool all the resources used by all the accounts into that
[[#Management]] account. 

Not only is it good for management it could also yield more savings since some
services get cheaper over time depending on the usage, and pooling all the
accounts in an organization makes it easier to reach the threshold.

## Using IAM In Organizations

Usually it is considered *best practice* to have specific [[iam]] accounts per
[[aws-account]], but having multiple accounts in an organization that you
control let's you use [[roles]] to authenticate to other accounts. 

This is used a lot more *in practice*, where companies might want to use
existing on-premises identities or an external idp. This way there is a single
[[#Member]] (or [[#Management]]) account that holds all the [[iam]] identities
and then use role switching to authenticate on other [[#Member]] accounts.

### Role Switching

When role switching you need to have role that trusts the [[#Management]]
account and has enough permissions to to whatever you need to do. By default
when you are [[#Adding Accounts]] and use the "Create Account" method instead of
inviting an account it creates a role called **OrganizationAccountAccessRole**.
