+++
tags = ['logging', 'regional-service']
+++

# CloudTrail

This service is somewhat similar to [[cloudwatch-logs]] in the sense that it
deals with logs, but that is it. This is a different service that has an
entirely different purpose. While [[cloudwatch-logs]] get log data from
applications CloudTrail logs api actions that affect an aws account.

## CloudTrail Event 

Any logs coming from an api/activity that affect an aws account is called a
**CloudTrail event**. There are 3 types of events: [[#Management Event]], 
[[#Data Event]], insight events (not covered yet).

By default CloudTrail Events gets stored for 90 days, free of charge. And by
default only [[#Management Event]] gets stored.

### Management Event

Anything that deals with the management of an aws account, creating EC2
instances, terminating an instance, etc, gets categorized as management
data.

### Data Event

Even data is any event that happens on or within a service. Like visiting the
uploading an object to S3, when a lambda function is being invoked, etc. This
creates a lot more data, that might not always be useful, which is why it is
disabled by default.

## Trails

In order to process [[#CloudTrail Event]]s in any way other than the 90 day
default history a trail has to be created. This will let you store and transfer
data into other services like S3 and [[cloudwatch-logs]].

A benefit of storing data into S3 is that you get around the 90 day holding
period of the data. Now that it is stored in S3 as a compressed json file and
you can have it there for as long as you want (while still paying for the
storage you are using).

Regional services usually log their data onto the region that they are created
in, so a CloudTrail Trail is needed there.

On the other hand global services always log their data to us-east-1. And in
order to get this these logs then the trail will have to enable global service
logging. I.E [[iam]], STS, CloudFront. 

### Regional Trail

This is a trail that gets created and configured to only log events for the
region it was created in.

### All Region Trail

This can be thought of as a collection of trails that exist in every single
region but managed through a single logical trail. This has the benefit of
automatically adding a new region if it gets created.

### Organizational Trail

It can store all the information that happens in [[organizations]] in one
centralized place.

## Limits

A really big limitation for CloudTrail is that it usually takes 5-15 minutes for
logs to make it into the management console, meaning this is **not a real time
service** so you cannot rely on the information that you get from here to make a
call on what is currently happening. 

## Pricing

There are some charges for CloudTrail which can be found
[here](https://aws.amazon.com/cloudtrail/pricing/).
