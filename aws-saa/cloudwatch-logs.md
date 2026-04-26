+++
tags = ['cloudwatch', 'public-service', 'regional-service']
+++

# CloudWatch Logs

This service allows you to **store**, **monitor**, and **access** logging data.
Logging data is, at its basic level, a time stamp and some application data.

## Integrations

Any services that integrate with CloudWatch logs can store logs, using [[roles]]
to access the service.

There are 3 ways to integrate CloudWatch onto an application:

1. Using the built in AWS services integrations, like EC2, lambda, R53, etc

2. For any applications outside of AWS then you can use the *unified CloudWatch
agent*

3. Use the AWS development kits and implement CloudWatch logging directly only
the application

## Metrics

Logs also have the ability create metrics and metric filters. This way you are
able to set up alarms based on metric filters so you are always alerted of
anything you set up. That could be resource utilization, failed logins, error
rates, etc.

## Structure 

CloudWatch has the following components:

### The service

The service of CloudWatch Logs itself is hosted in a region. Now while the
service is hosted in a region the [[#Logging Sources]] do not need to be part of
that region. You are able to use CloudWatch as a centralized place to store logs
without having your other application hosted in the same place.

### Logging Sources

The starting point / source when creating logs. This includes any aws services, 
mobile applications, servers, api endpoint, etc.

### Log Events

All the information that gets sent by [[#Logging Sources]] onto CloudWatch.
Usually have the format `YYYYMMDDHHMMSS MESSAGE`.

### Log Stream

A localize place where [[#Log Events]] from a source get stored. There is one
stream per source, which different service instances will be treated as
different sources.

### Log Group

A set of [[#Log Stream]], it can be 1 or more. 

Groups serve 2 important purposes:

1. define metric filters which can then be used for alarms
2. define configurations, config includes deciding how long to keep logs and 
permissions
