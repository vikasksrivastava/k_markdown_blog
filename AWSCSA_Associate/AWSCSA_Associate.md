# AWS Certified Solution Architech - Associate

<!-- TOC START min:1 max:3 link:true update:true -->
- [AWS Certified Solution Architech - Associate](#aws-certified-solution-architech---associate)
  - [Introduction](#introduction)
  - [AWS Organisation](#aws-organisation)
    - [AWS Account and Physical Organisation](#aws-account-and-physical-organisation)
    - [Physical Organisation](#physical-organisation)
    - [AWS Terminology](#aws-terminology)
  - [AWS Access Management](#aws-access-management)
    - [IAM Policy](#iam-policy)
    - [IAM groups](#iam-groups)
    - [IAM Roles](#iam-roles)
  - [AWS Interfaces](#aws-interfaces)
  - [AWS Networking](#aws-networking)
  - [Server-Based Compute Services](#server-based-compute-services)
  - [Server**less** Compute Services](#serverless-compute-services)
  - [Advanced Networking](#advanced-networking)
  - [Advanced VPC Networking](#advanced-vpc-networking)
  - [Network Troubleshooting](#network-troubleshooting)
  - [Storage Services](#storage-services)
  - [Hybrid Environments](#hybrid-environments)

<!-- TOC END -->

## Introduction

## AWS Organisation

### AWS Account and Physical Organisation

This represents how how you manage multiple services and account managment.


![](assets/markdown-img-paste-20180317155120909.png)

 > The above picture shows a organisation of the AWS Users and Groups and the different ways (You can have different groups for `PROD` and `QA`) , Console or CLI they can use to login and manage the AWS Cloud.

### Physical Organisation

At a very high level AWS can be broken down into two main blocks

**`AWS Regions`** : These are grouping of independenly separated datacenters in a specific geographic regions know as `Availabilty Zones`.
**`AWS Edge Location`** : It is a Datacenter whic does not contain any AWS Services ; Instead it is used to deliver contents to parts of the world. `CloudFront`

> Not All AWS Services are availaible globally , one of the example of a Global Service is the `IAM`

![](assets/markdown-img-paste-20180317155925901.png)

An `AWS Region` has multiple `Availabilty Zones`

![](assets/markdown-img-paste-20180317160605765.png)

Now within each `Availabilty Zone` there can be multiple `Datacenters`

`Availabilty Zones` are **phyically sperated** to each other but **have high speed connection between them** to provide **Fault Tolerance**

> So as an example `S3` is replicated accross all `Availabilty Zones` and all `Datacenters` for **reliability and high availaibility**.

![](assets/markdown-img-paste-20180317160708670.png)

Now as we further move ahead , the `VPC` is the

![](assets/markdown-img-paste-20180317161347849.png)

### AWS Terminology

`High Availability (HA)` This means creating and managing the ability to automatically “failover” to a secondary system if the primary system goes down for any reason as well as **eliminating all single points of failure** from your infrastructure.

`Fault Tolerance` this means infrastructure that is designed in such a way that **when one component fails**(be it hardware or software), a **backup component takes over operations immediately** so that there is no loss of service.

`Scalability` is the capability to scale out **easily**.

`Elasticity` the ability to **scale-up** as well as **scale-down**

-------

## AWS Access Management

Now lets look at the `IAM` Components where you manager Users, roles and groups, IAM Consistes of :

`IAM User`
`IAM Groups`
`IAM Policy`
`IAM Role `
`IAM API Keys`
`IAM Password Policy`

![](assets/markdown-img-paste-20180317162435923.png)

> IAM is Global and does not require a region selection.

Now once you have enable IAM , you can use the link show in the picture below to login

![](assets/markdown-img-paste-20180317163005646.png)

### IAM Policy

An IAM Policy , looks like this. Note that `Deny` will have a precedence over `Allow`.

![](assets/markdown-img-paste-20180317163328797.png)

An example of where you can see the policy in detail and whats how it is organised

![](assets/markdown-img-paste-20180317163621375.png)

### IAM groups

Groups are like AD Groups in a company where you segregate users into respective division , like HR, Finace etc .

So now the `policies` can be attached to the `groups` directy.

### IAM Roles

Look at the example below and notice how that all the Users and Roles are created at the IAM Level.

`Non AWS Account Holder` : Now what we integrate AWS with the AD in a company. The users from AD who are **authenticated via SAML** now need to be mapped to `Role` to be able to do things in the AWS

`EC2 instance needing access to S3`

> An EC2 instance can only have one role attached to it .

![](assets/markdown-img-paste-20180317164404537.png)

#### Role Assumption

Now lets say , the users below in the `DEV` group need access to the  resources in the `PROD`, then can **assume** a `Role` and be able to access the resource in `PROD`.

![](assets/markdown-img-paste-20180317165031723.png)

**How does the above assumption happen?**

An `IAM Policy` is attached to an `IAM Role` which is then assigned to the `User` or `Resource` which needs acces.

![](assets/markdown-img-paste-20180317165340821.png)



-------

## AWS Interfaces
-------

## AWS Networking
-------

## Server-Based Compute Services
-------

## Server**less** Compute Services
-------

## Advanced Networking
-------

## Advanced VPC Networking
-------

## Network Troubleshooting
-------

## Storage Services
-------

## Hybrid Environments
