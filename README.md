# AWS-Certified-Cloud-Practitioner-Notes
Studying for the AWS CCP exam! This repo serves as a personal resource.. I will include AWS documentation and other resources used when applicable.

# Examination Content
| Domain | % of Examination|
|--------|-----------------|
|Cloud Concepts| 26%       |
|Security and Compliance| 25%|
|Technology| 33%|
|Billing and Pricing| 11%|

## Domain One: Cloud Concepts

https://d1.awsstatic.com/whitepapers/aws-overview.pdf
https://aws-certified-cloud-practitioner.fandom.com/wiki/1.3_List_the_different_cloud_architecture_design_principles

__Objectives:__
1. Define the AWS Cloud and its value proposition
2. Identify aspects of AWS Cloud economics
3. List the different cloud architecture design principles

### Cloud Concepts: Defining AWS Cloud and Its Value Proposition

**What is AWS Cloud?:**

- AWS Cloud provides over 175 cloud computing services that range from computing, storage, databases, networking, and more.
  - Cloud computing allows on-demand delivery of IT resources through a cloud platform like AWS. 
  - AWS Cloud provides a reliable, scalable, low-cost infrastructure platform that is utilized by hundreds of thousands of businesses in 190 countries
  - AWS owns and maintains the network-connected hardware required for these services, allowing the user to privision and use what they need through a web application.

**AWS Value Proposition:**

|Principle| Concepts|
|---------|---------|
|Agility|Speed, Experimentation, Innovation|
|Elasticity|Scale on demand, Eliminate wasted capacity|
|Flexibility|Broad set of products, Low cost to entry|
|Security| Amazon acquired compliance certifications, Shared responsibility model|

### Cloud Concepts: Identify Aspects of AWS Cloud Economics:

  1. Trade capital expense for variable expense: pay for how much you consume
  2. Benefit from massive economies of scale: the AWS large customer base allows lower prices
  3. Stop guessing capacity: access as much or as little resources as you need
  4. Increase speed and agility: in a cloud environment, cost and time to develop decreases due to on-demand services
  5. Stop spending money running and maintaining data centers: a cloud computing environment allows you to focus on other projects than handling in-person infrastructure
  6. Deploy applications globally: AWS allows applications to be deployed in multiple regions with few clicks: customers can enjoy low latency and a better experience. 

### Cloud Concepts: List the Different Cloud Architecture Design Principles:

__Well-Architected Framework:__
|Pillar|Description|
|------|-----------|
|Security| Ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies.|
|Reliability| Ability of a system to recover from infrastructure or service failures, dynamically acquire computing resources to meet demand, and minigate disruptions like misconfigurations.|
|Performance Efficiency| Ability to use computing resources efficiency to meet system requirements, and to maintain that efficiency as demand changes and technologies evolve.|
|Cost Optimization| Ability to avoid or eliminate unneeded cost or suboptimal resources.|
|Operational Excellence| Ability to run and monitor systems to deliver business value and improve supporting processes and procedures.|

__Core Principles Outline:__
1. Scalability
2. Disposable Resources Instead of Fixed Servers
3. Automation
4. Loose Coupling
5. Services, Not Servers
6. Databases
7. Managing Increasing Volumes of Data
8. Removing Single Points of Failure
9. Optimize for Cost
10. Caching
11. Security

***Scalability:***

Scability is the ability to scale without changing design. In AWS, scalability is achieved by scaling-out. AWS technology components can be thrown out when they fail, or they can be grown by adding more when demanded. 

There are two types of scaling:
  1. Horizontal Scaling: An increase in the number of resources.
  2. Vertical Scaling: an increase in the capabilities of the resource: faster CPU, more memory, more storage, etc.)


***Disposable Resources:***

Resources should be treated as temporary disposable resources rather than fixed permanent on-premises resources.

AWS focuses on *immutable infrastructure*: a server once launched is never updated through its lifetime. Updates are performed on a new server with the latest configuration, ensuring resources are in a cosistent state with easier rollbacks.

AWS provides different ways to instantiate resources in an automated and repeatable way:
  1. Boostrapping: scripts for configuration and setup
  2. Golden Images: Snapshot of state of the resource. Allows faster start times and removes dependencies to configuration services or third-party repositories.
  3. Containers: AWS supports docker images through Elastic Beanstalk and ECS.
  4. Infrastructure as Code: AWS assets are programmable. 


***Automation:***

AWS Cloud allows automation of different events, allowing for improvements in system stability and efficiency. Some AWS resources that you can automate include: AWS Elastic Beanstalk, Auto Scaling, AWS CloudWatch Events, and more.


***Loose Coupling:***

Loosely coupled architectures reduce interdependencies, so a failure in a component does not cascade to other components.

  1. Asynchronous Integration: does not involve point-to-point interaction, but through a durable storage layer like SQS or Kinesis
  2. Service Discovery: allows new resources to be launched or terminated at any point in time
  3. Well-Defined Interfaces: allows components to interact through specific, technology-agnostic interfaces


***Services, Not Servers:***

AWS architecture can leverage a broad set of compute, storage, database, analytics, application, and deployment services.

***Databases:***

AWS offers the following services:

1. Relational Databases (RDS)
    1. Data is normalized into relations, called tables, and each relation is a collection of unordered tuples, called rows. Relational databases can be queried through SQL and can be scaled vertically. The RDS service can be set up across a hybrid environment (distributed across both a company's data center and an AWS VPC).
2. Document Databases (DynamoDB)
    1. Document databases provide a flexible data model that can scale horizontally, utilizing a variety of data models like graphs, key-value pairs, and JSON/XML documents. The term NoSQL is often used to describe these databases, and recently the term has been rebranded as "Not-only SQL".
3. Data Warehouses (Redshift)
    1. AWS Redshift acts as a data warehouse, allowing for analysis and reporting of large amounts of data. 


***Remove Single Points of Failures:***

A system is highly available when it can withstand the failure of an individual or multiple components (servers, hard disks, etc.). Recovery and disruption reduction can be automated in AWS.

***AWS Cost Optimization:***

AWS cloud architecture can be designed for cost optimization by selecting the right configurations and storage solutions or by utilizing Auto Scaling.


***Caching:***

Caching improves application performance and increases the cost efficiency of an implementation.

1. Application Data Caching
    1. Provides services that store and retrieve information from fast, managed, in-memory caches
    2. ElastiCache makes it easy to deploy, operate, and scale an in-memory cache in the cloud. It supports two open-source in-memory caching engines: Memcached and Redis.
4. Edge Caching  
    1. Allows content to be served by infrastructure that is closer to viewers, lowering latency and giving high data transfer rates to end users at scale.
    2. CloudFront is Content Delivery Network (CDN) consisting of multiple edge locations, that allows copies of static and dynamic content to be cached.  


***Security:***

See the AWS Security Whitepaper: https://docs.aws.amazon.com/whitepapers/latest/introduction-aws-security/introduction-aws-security.pdf

AWS works on a shared seucrity responsibility model:

1. AWS is responsible for the seucrity of the underlying cloud infrastructure
2. AWS users are responsible for securing workloads deployed in AWS

AWS provides ample security features:

1. IAM to define a set of policies and assign them to users, groups, and resources
2. IAM Roles to assign short term credentials to resources
3. Amazon Cognito for mobile applications allows client devices to get controlled access to AWS resources through temporary tokens
4. VPC to isolate parts of infrastructure through the use of subnets, security groups, and routing controls
5. WAF to protect web applications from SQL injections and other vulnerabilities
6. CloudWatch logs to collect logs
7. CloudTrail for auditing AWS API calls
