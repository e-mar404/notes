+++
tags = ['aws-fundamentals']
+++

# Disaster Recovery

A set of policies, tools and procedures to **enable the recovery** or
**continuation** of **vital** technology infrastructure and systems **following
a natural or human-induced disaster**.

Planning needs to happen in case of any disaster happening. This mainly means
having a backup of services and compute in a different location in case of a
disaster damaging a significant portion of the production infra.

All of this needs to be available in very constrained situations such as
bringing up a system from no internet connection (might need local admin creds
for things), or having enough login creds for the back up location to use. But
it is very important that this information is not only documented but that
people know where to go in case of a disaster.
