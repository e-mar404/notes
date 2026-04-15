+++
tags = ['aws-fundamentals', 'global-service', 'DNS']
+++

# Route 53

It has 2 main purposes:

1. Register domains
    - In order to do this aws has relationships with the all of the mayor domain
      registers.

2. host zones (managed **nameservers**)
    - When registering a domain, route 53 will create the zone file and allocate
    nameservers with the zone file

Route 53 is a global service so there is a "single" database for all aws
regions. This means that the service is [[globally-resilient]].

## Hosted Zones

The zone files are called **hosted zones** in aws terminology because they are
hosted on aws managed nameservers.

Hosted zones are able to be either public or private (linked to vpc(s)).
