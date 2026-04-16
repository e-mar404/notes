+++
tags = ['aws-fundamentals']
+++

<!--toc:start-->
- [Quiz](#quiz)
<!--toc:end-->

# Quiz


1. What permission options does an AMI have?
A: Punic access, owner only, specific AWS accounts

2. What is **NOT** stored in an AMI?
    
    a) boot volume
    b) data volumes
    c) AMI permissions
    d) block device mapping
    e) instance settings
    f) network settings

A: e, f

3. EC2 is an example of which service model?
    
    a) PAAS
    b) IAAS
    c) SAAS
    d) DBaaS
    e) FaaS

A: b) 

4. What is true of an AWS public service?

    a) located in the public internet zone
    b) located in the aws public zone
    c) located in a vpc
    d) publicly accessible by anyone
    e) anyone can connect, but permissions are required to access the service

A: b, e 

5. What is true of an AWS private service?

    a) located in the public internet zone
    b) located in the aws public zone
    c) located in a vpc
    d) accessible from the vpc it is located in
    e) accessible from any other VPC
    f) accessible from other VPCs or on-premises networks as long as private
    networking is configured

A: c, d, f

6. What is true of Simple Storage Service (S3)?

    a) S3 is an AWS Public Service
    b) S3 is a private service
    c) S3 is an web scale block storage system
    d) S3 is a object storage system
    e) Buckets can store a limit of 100TB of data
    f) Buckets can store an unlimited amount of data

A: a, d, f

7. What is a CloudFormation Logical Resource?
A: a resource defined in a CloudFormation template

8. What is a CloudFormation physical resource?
A: a physical resource created by creating a CloudFormation stack

9. What is a simple and correct definition of High Availability?
A: a system which maximizes uptime

10. Which of the following is a correct definition of fault tolerant system?

    a) A system which uses automation to return a service to operational status
       with little user disruption 
    b) A system which has a 99.999% uptime 
    c) A system which allows failure, and can continue operating without 
       disruption
    d) A system which has regular and reliable system backups and restore
       processes

A: c

11. How many DNS root servers exist?
A: 13

12. Who manages the DNS root servers?
A: 12 large organizations

13. Who manages the DNS root zone?
A: IANA (Internet Assigned Numbers Authority)

14. Which DNS record type converts a host into an IPv4 address?
A: A Record

15. Which DNS record type is how the root zone delegates control of `.org` to
the .org registry?
A: NS Record

16. Which type of organization maintains the zones for a TDL (eg `.org`)?
A: A registry organization

17. Which type of organization has relationships with the `.org` TLD zone
manager allowing domain registration?
A: A registrar organization

18. How many subnets are in a default VPC?
A: there are as many subnets as there are AZ in the region the vpc is located in

19. What is the IP CIDR of a default VPC?
A: 172.31.0.0/16

