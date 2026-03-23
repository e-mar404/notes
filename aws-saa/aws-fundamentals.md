+++
deck: aws-fundamentals
+++

# public vs private AWS services

1. Public and private service refer primarily to the networking perspective (T/F)

A: True

2. What is an AWS Private zone?

A: A section of the AWS network that is only accessible by other internal aws
services

3. What is an AWS Public zone?

A: A section of the AWS network that the public internet can access

4. What can you use to connect on-premises infrastructure to VPC on the AWS private
zone?

A: You can use a VPN or AWS direct connect

# AWS Global Infrastructure

1. What is an AWS region?

A: A place in the world that holds all the available AWS services, and there are
multiple around the world

2. What is an AWS edge location?

A: A smaller more limited location that does not hold any compute resources and
are used for caching and networking purposes.

3. What are the 3 main benefits of AWS regions?

A: 
    - geographical/Disaster isolation
    - geopolitical isolation
    - Location control 

4. What is an Availability Zone?

A: A separate smaller section that is a part of an AWS region

5. What does it mean if a service is globally resilient?

A: The service exists across all AWS regions and it would take a complete global
AWS infrastructure failure for the service to not be available any more

6. Examples of Globally resilient service (2)

A: 
    - IAM
    - Route 53

7. What does it mean if a service is region resilient?

A: The service is able per region and would take a complete region failure for 
the service to not be available any more

9. What does it mean if a service is AZ resilient?

A: The service exists per Availability Zone and would take a complete AZ failure
for the service to not be available any more

# AWS default Virtual Private Cloud (VPC)

1. VPC is a:

    A) Regional Service
    B) Global Service

A: A) Regional Service

2. A VPC is ____

A: a virtual network inside AWS

3. What are the types of VPC?

A: default and custom VPCs

4. How many default VPCs are there?

A: There is one default VPC per region

5. What is the default VPC CIDR? 

A: 172.31.0.0/16

6. What is the general structure for the default VPC?

A: 
    - private and isolated unless configured otherwise
    - pre-configured to have a /20 subnet for each AZ for the region
    - contain an internet gateway, defualt security group & NACL
    - subnets assign public IPv4 addresses

# Elastic Compute Cloud (EC2)

1. What is IAAS?

A: Infrastructure as a service, EC2 is a type of IAAS

2. What type of resilience does EC2 have?

A: AZ resilience, an EC2 gets started in an availability zone so it will take
that AZ to fail for the service to stop

3. What is the high level overview of billing for EC2?

A: you get charged for cpu, ram, storage, and networking. If EC2 container is
stopped then you only get charged for the storage.

4. What are the 3 main states of an EC2 instance?

A: running, stopped, terminated

5. What does AMI stand for and what is it used for?

A: Amazon Machine Image, it is used for creating and running EC2, similar to
docker images

6. What are the 3 main parts of an AMI? 

A: Permissions, Root Volume, block device mapping

# S3 basics

1. What does S3 stand for?

A: Simple Storage Service

2. S3 is a:

    A) Regional Service
    B) Global Service

A:  B) Global Service

3. What type of resilience does S3 have?

A: Regional resilience

4. What is S3 used for?

A: for most types of media and data storage, as well for most input into aws
service and output from aws services

5. S3 should be the default choice for storage (T/F)

A: True

6. What components does an S3 object have?

A: 
    - keys = file name
    - value = data/content
    - metadata
    - version id
    - access control
    - subresources

7. What is the size range of a single object, and how many objects can a bucket
store?

A: an object's size can range between 0 bytes - 5 TB and there can be an
unlimited amount of objects in a bucket

8. By default, data on a bucket does not leave the region it was configured for (T/F)

A: True

9. S3 buckets require the bucket name to be ___.

A: 
    - globally unique
    - between 3 - 63 chars, all lowercase and no underscores
    - not formatted like an ip
    - start with a letter or number

10. What is the underlying file structure of an S3 bucket?

A: it is a flat file structure, any directories that are shown on the console
are "made up". Object name looks like this /dir/name.jpg and then a directory
can be made out of the name. But everything is at the same level with no folders

11. What is the limit of the number of buckets per account?

A: soft limit of 100 and hard limit of 1000 (aws rep needed)

12. What are some S3 anti-patters/patterns?

A:
    - should not be used as a network file share
    - s3 bucket cant be mounted (ie S:\ or /mnt/dev)
    - great for large scale storage
    - good to offload data from EC2 or other services

# Cloud Formation

1. What is cloud formation used for?

A: it is used to create aws resources in an easy and repeatable manner with
templates (written in yaml/json)

2. What are some key components for Cloud Formation templates?

A: 
    - AWSTemplateFormatVersion
    - Description: free text, must be directly after version id if present
    - Metadata: control ui
    - Parameters: input fields on the ui when using template
    - Mappings: key/value pairs used for lookups
    - Conditions: creates contidions to be referenced in other components
    - Transform
    - Resources: list resourced to create (only required field)
    - Outputs: output to show the console after template is executed

3. How does a stack relate to a template in cloud formation?

A: a stack gets created through a template and it manages all the resources and
changes done by a template

4. What is a logical resource?

A: it is a resource that the stack references

5. What is the relationship between physical resources and stacks in cloud
formation?

A: the stack maps a logical resource into a physical resource that gets created
based on the template and keeps them synced to the state of the stack

# Cloudwatch

1. What is the main responsibilities of cloudwatch?

A: collect and monitor data for services. It collects metrics, logs and events

2. You cannot use cloudwatch to monitor services outside of AWS (T/F)

A: False, you can install the cloudwatch agent to record metrics for other cloud
infra or on-prems hardware 

3. What is a Cloudwatch namespace?

A: A way to categorize metrics

4. What is the AWS/<service> Cloudwatch namespace?

A: A reserved namespace by aws to dump all the metric collected from aws
services

5. What are dimensions in Cloudwatch?

A: dimensions are ways to separate metrics with different criteria, this is
important data to filter down metrics to only see what is relevant in the moment
