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
