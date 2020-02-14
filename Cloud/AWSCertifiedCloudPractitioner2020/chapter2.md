# Chapter 2 Cloud Concepts And Technology

## 2.1 What Is Cloud Computing?
Cloud computing is the on-demand delivery of compute, datebase storage, applications, and other IT resources through a cloud services platform via the Internet with pay-as-you-go pricing.

### The 6 advantages of cloud computing
#### 1 - Trade capital expense for variable expense
Pay only for what you use
#### 2 - Benefit from massive economies of scale
#### 3 - Stop guessing about capacity
Scale with your business needs
#### 4 - Increase speed and agility
#### 5 - Stop spending money running and maintaining data centers
#### 6 - Go global in minutes
Lower latency and a better experience at a minimal cost

### 3 Types of Cloud Computing
- Infrastructure As A Service (IAAS) => EC2
- Platform As A Service (PAAS) => Elastic Beanstalk
- Software As A Service (SAAS) => Gmail

### 3 Types of Cloud Computing Deployments
- Public Cloud - AWS, Azuez, GCP
- Hybrid - Mixture of public and private
- Private Cloud (Or On Premise) - Openstack or Vmware

### Market share
Amazon (47%), Azure (22%), Alibaba (8%), GCP (7%), Other (16%)

## 2.2 Around The World With AWS
### AWS Global Infrastructure
19 Regions & 57 Availability Zones - 2018/12

24 Regions & 72 Availability Zones - 2019

Availability Zone => a (or several) data center

Regions (physical location) => 2 (or more) AZ

### Edge Locations
Endpoints used for caching content. Consists of CloudFront, Content Delivery Network (CDN).

### Exam Tips
#### Choosing the right AWS Region
- Data Sovereignty Laws
- Latency to end users
- AWS Services

## 2.3 Let's Log In To AWS
Support plans : basic, developer (29$/month), business (100$/month), entreprise (15000$/month)

## 2.5 Setting Up On A Windows PC

## 2.6 Setting Up A Billing Alarm
Services->Cloud Watch->Billing

## 2.7 Let’s Start To Cloud! Identity Access Management (IAM)
multi-factor authentication (MFA)

Access management : Programmatic access (command line), AWS Management CONSOLE access, SDK (Software Developers Kit)

### Exam Tips
- Do not specify a region when dealing with IAM.
- The root account always has full administrator access.
- Apply a policy (consist of JSON, Java Script Object Notation) to a group to set permissions.

## 2.8 S3 101
S3 - Simple Storage Service, from 2006-2007

- A safe place to store flat files (file doesn't change)
- Object-based storage, opposite to block based storage
- The data is spread across multiple devices and facilities

### The basics of S3
- S3 is Object-based
- Files can be from 0 Bytes to 5 TB
- Unlimited storage
- Files stored in buckets (folder in cloud)
- S3 is a universal namespace (unique name globally)
- Receive a HTTP 200 code if upload successful

### S3-Objects
Objects consist of the following :
- Key (name of object)
- Value (data)
- Version ID
- Metadata (data about data you are storing)
- Subresources (Access Control Lists, Torrent)

### Data Consistency Model for S3
- Read after Write consistency for PUTS of new Objects (upload and read immediately OK)
- Eventual Consistency for overwrite PUTS and DELETES (takes time to propagate)

### S3 - Guarantees
- Built for 99.99% availability for S3 platform
- Amazon guarantee 99.9% availability
- Amazon guarantees 99.999999999% (11 * 9) durability for S3 information

### S3 - Features
- Tiered Storage Available
- Lifecycle Management
- Versioning
- Encryption
- Secure data using Access Control Lists (file level) and Bucket Policies (bucket level)

### S3 Storage Classes
1.S3 Standard

2.S3 - IA (infrequently accessed), more rapid when needed

3.S3 One Zone - IA

4.S3 - Intelligent Tiering (machine learning)

5.S3 Glacier, for data archiving (from minutes to hours)

6.S3 Glacier Deep Archive, for deep data archiving (12hrs)

### S3 - Charges
- Storage
- Requests
- Storage Management Pricing
- Data Transfer Pricing
- Transfer Acceleration (edge location)
- Cross Region Replication Pricing (disaster recovery)

### Exam Tips
- S3 is object-based
- Files from 0 Bytes to 5 TB
- Unlimited storage
- Files stored in Buckets
- S3 is a universal namespace
- https://s3-eu-west-1.amazonaws.com/acloudguru
- Not suitable to install an OS
- HTTP 200 when upload success
- Key-Value pairs
- Consistency for PUTS
- Eventual Consistency for overwrite PUTS and DELETES
- 6 different S3 storage

## 2.9 Let's Create An S3 Bucket!
Restricting Bucket Access
- Bucket Policies
- Object Policies
- IAM Policies to Users & Groups

## 2.10 Let's Create A Website On S3
S3 can host STATIC websites

## 2.11 Let's Explore CloudFront
A content delivery server (CDN) is a system of distributed servers that deliver web content.

### CloudFront - Key Terminology
- Edge location : cache content
- Origin : S3 Buckets, EC2 Instance, etc.
- Distribution : a collection of edge locations

- Web distribution
- RTMP : Media Streaming

### Exam Tips
- Edge locations are not just READ only.
- Objects are cached for the life of the TTL (Time To Live)
- Clear cached objects will be charged

## 2.12 EC2 101
EC2 - Elastic Compute Cloud, a virtual server in the cloud.

### EC2 pricing models
1. On demand
2. Reserved : capacity reservation
3. Spot
4. Dedicated Hosts

### On Demand pricing
- low cost and flexibility
- applications cannot be interrupted
- applications being developped or tested on EC2 for the first time

### Reserved pricing
- steady state or predictable usage
- reserved capacity
- make upfront payments to reduce their total computing costs even further

1. Standard Reserved instances
2. Convertible Reserved instances
3. Scheduled Reserved instances

### Spot pricing
- flexible start and end times
- feasible at very low compute prices
- urgent computing needs for large amounts of additional capacity

### Dedicated Hosts pricing
- regulatory requirements that may not support multi-tenant virtualization
- licensing which does not support multi-tenancy or cloud deployments
- Can be purchased On-Demand
- Can be purchased as a Reservation for up to 70% off the On-Demand price

### EC2 Instance Types - Mnemonic
FIGHT DR. MCPXZ

### EBS
The virtual hard disks in the cloud that EC2 uses.

#### SSD
- GP2, General Purpose SSD
- IO1, Provisioned IOPS SSD

#### Magnetic
- ST1, Throughput Optimized HDD
- SC1, Cold HDD

### Exam Tips
a virtual server in the cloud

1. On demand
2. Reserved : capacity reservation
3. Spot
4. Dedicated Hosts

FIGHT DR. MCPXZ

GP2, IO1, ST1, SC1

## 2.13 Let's Use EC2

### Exam Tips
- Use a private key to connect to EC2

## 2.14 Using The Command Line

## 2.15 Using Roles

### Exam Tips
- Roles are much more secure than using access key id's and secret access keys and are easier to manage.
- Apply roles to EC2 instances at any time.
- Roles are universal.

## 2.16 Let's Build A Web Server

## 2.17 Let's Use A Load Balancer
### Exam Tips
- Application Load Balancers, Intelligent Decisions
- Netword Load Balancers, Extreme Performance
- Classic Load Balancers, Test & Dev

## 2.18 Databases 101
Relational database on AWS - RDS (OLTP)
- SQL Server
- Oracle
- MySQL Server
- PostgreSQL
- Aurora
- MariaDB

### RDS key features
- Multi-AZ :for disaster recovery
- Read Replicas : for performance

### Non relational database
- Collection = Table
- Document   = Row
- K-V pairs  = Fields

Columns can vary, this will not affect other rows in the DB

Non-Relational database on AWS - DynamoDB

### OLTP vs OLAP
OLTP : online transaction processing
OLAP : online analytics processing

Amazon's Data Warehouse (BI) Solution is called Redshift

ElastiCache : cache engine in the cloud (web service) that caching your most common queries. 2 different caching engines : 
- Memcached
- Redis

## 2.19 Let's provision an RDS instance

## 2.20 Autoscaling

## 2.21 Let's Register A Domain Name
DNS : Domain Name System

Use Alias to redirect

Amazons DNS Service is called Route53, it's global.
- direct trafic
- register a domain name

## 2.22 Elastic Beanstalk
Quickly deploy and manage applications in AWS without worrying about the infrastructure.

## 2.23 CloudFormation
A service that helps you model and set up your AWS resources. It takes care of provisioning and configuring those resources for you.

Elastic Beanstalk and CloudFormation are both FREE services, however the resources they provision are not free.

EB is limited in what it can provision and is not programmable. CF can provision almost any AWS service and is completely programmable.

## 2.24 Architecting For The Cloud Best Practices - Part 1
