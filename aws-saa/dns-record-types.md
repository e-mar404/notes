+++
tags = ['aws-fundamentals', 'dns']
+++

# DNS Record Types

## Nameserver (NS) Records

This allows delegation to occur inside DNS. For instance, there are NS records 
in in the .com zone that point to amazon servers that host the amazon.com zone
and in here is where aws will put all the other records that get created from
[[route-53]].

## A and AAAA Records

These records map hostname to IP addresses. The difference is what type of IP
the record points to. A records point to IPv4 and AAAA records point to IPv6.

## CNAME Records

Stands for canonical name. This record map host to hosts. For instance if a
server handles multiple jobs, so if it handles mail, ftp, then they can point to
the hostname of the server and then it will be redirected to the ip address that
the hostname resolves to.

## MX Records

Mainly used for email and finding what server to connect to through the smtp
protocol. 

This record has 2 parts:

1. Priority
    - lower values are used first (the lower the value the higher priority)
2. Value
    - it can be either a host, assumed to be part of the same zone, or a
      different domain outside the zone
    - if there is a dot at the right of the host then it is treated as a
      separate domain

## TXT Records

A common usage for this record is to prove domain ownership by adding an
arbitrary piece of text.

Also able to fight spam to specify what entities are allowed to send email on
your domains behalf so if there is any email from anyone else then it can be
filtered properly.
