# Identity Access Management & S3
## 3.1 IAM 101
Manage users and their level of access to AWS.

### Features
- Centralised control
- Shared access
- Granular permissions
- Identity Federation
- Multifactor authentication
- Provide temporary access for users/devices and services
- Set up own password rotation policy
- Integrates with many AWS services
- Supports PCI DSS Compliance (credit card)

### Key terminology
1. Users
2. Groups
3. Policies
4. Roles

## 3.2 IAM Lab
Region : global

### Exam Tips
- IAM is universal
- Root account : the account created when first setup the AWS account
- New users : NO permissions when first created
- New users : Access Key ID & Secret Accesss Keys when first created. For accessing AWS via APIs and Command Line
- You only get to view these once
- Always setup Multifactor Authentication on your root account
- You can create and customise your own password rotation policies

## 3.3 Create A Billing Alarm

## 3.5 S3 101
Simple Storage Service. With a simple web servcies interface to store and retrieve any amount of data from anywhere on the web.

### The basics
- A safe place to store files (in Buckets).
- Object-based storage (0-5TB, unlimited storage).
- Data is spread multiple devices and facilities.

- S3 is a universal namespace
- HTTP 200 code if upload successful
- Key, Value, Version ID, Metadata, Subresources (Access Control Lists, Torrent)

### Data consistency
- Read after Write consistency for PUTS
- Eventual consistency for overwrite PUTS and DELETES

### Guarantees
- 99.99% : DESIGNED FOR
- 99.9% : SLA GUARANTEE
- 99.999999999% : durability for S3 information

### Features
- Tiered Storage Available
- Lifecycle Management
- Versioning
- Encryption
- MFA Delete
- Secure data using Access Control Lists and Bucket Poicies

### Storage Classes
1. S3 Standard : 99.99% availability, 99.999999999% durability
2. S3 IA : Infrequently Accessed
3. S3 One Zone - IA : lower-cost option for infrequently accessed data, but do not require the multiple AZ data resilience
4. S3 Intelligent Tiering : designed to optimize costs by automatically moving data to the most cost-effective access tier
5. Glacier : a secure, durable, and low-cost storage class for data archiving. Retrieval times configurable from minutes to hours.
6. Glacier Deep Archive : lowest-cost storage (12 hours for retrieval)

### Charges
- Storage
- Requests
- Storage Management Pricing
- Data transfer
- Transfer acceleration
- Cross region replication

### S3 transfer acceleration

### Exam tips
- S3 is object-based
- Files from 0 to 5 TB
- Unlimited storage
- Files are stored in Buckets
- S3 is a universal namespace
- Not suitable to install an OS
- HTTP 200
- MFA Delete
- Key, Value, Version ID, Metadata, Subresources
- Data consistency

Read the S3 FAQ

## 3.6 Let's Create An S3 Bucket
### Exam tips
- Buckets are a universal name space
- HTTP 200 code
- S3, S3-IA, S3-IA (one zone), Glacier
- Bucket ACL, Bucket policies

## 3.7 S3 Pricing Tiers
### Exam tips
Understand how to get the best value out of S3

## 3.8 S3 Security And Encryption
### The basics
All newly created buckets are private by default.
- Bucket policies
- ACL

S3 buckets can be configured to create access logs which log all requests made to the S3 bucket.

Encryption in transit is achieved by
- SSL/TLS

Encryption at rest (server side) is achieved by
- S3 managed keys - SSE-S3 (Amazon manage)
- AWS key management service, managed keys - SSE-KMS (you and Amazon)
- Server side Encryption with customer provided keys - SSE-C

Client side encryption

## 3.9 S3 Version Control
### Using versioning with S3
- Store all versions of an object (all writes & delete)
- Great backup tool
- Once enabled, versioning cannot be disabled only suspended
- Integrates with lifecycle rules
- Versioning's MFA delete capability can be used to provide an additional layer of security

## 3.10 S3 Lifecycle Management and Glacier
Lifecycle rules enable you to automatically transition objects
### Exam tips
- Automates moving your objects between the different storage tiers
- Can be used in conjunction with versioning
- Can be applied to current versions and previous versions

## 3.11 AWS Organizations
### Definition
An account management service that enables you to consolidate multiple AWS account into an organization that you create and centrally manage.
### Advantages of consolidated billing
- One bill per AWS account
- Easy to track charges and allocate costs
- Volume pricing discount
### Exam tips
- Always enable multi-factor authentication on root account
- Always use a strong and complex password on root account
- Paying account should be used for billing purposes only
- Enable/Disable AWS services using Service Control Policies (SCP) either on OU or on individual accounts

## 3.12 Sharing S3 Buckets Between Accounts
### 3 different ways
- Using bucket policies & IAM. Programmatic Access Only
- Using bucket ACLs & IAM (individual objects). Programmatic Access Only
- Cross-account IAM roles. Programmatic and console access

## 3.13 Cross Region Replication
### Exam tips
- Versioning must be enabled on both the source and destination buckets
- Regions must be unique
- Files in an existing bucket are not replicated automatically
- All subsequent updated files will be replicated automatically
- Delete markers are not replicated
- Deleting individual versions or delete markets will not be replicated

## 3.14 Transfer Acceleration
S3 transfer acceleration utilises the CloudFront Edge Network to accelerate your uploads to S3.

## 3.15 CloudFront Overview
### Definition
A content delivery network (CDN) is a system of distributed servers that deliver webpages and other web content to a user based on the geographic locations of the user, the origin of the webpage, and a content delivery server.

### Key terminology
- Edge location : the location where content will be cached
- Origin : origin of all the files that the CDN will distribute. This can be an S3 bucket, an EC2 instance, an Elastic Load Balancer, or Route53
- Distribution : consists of a collection of Edge Locations
  - Web distribution : Typically used for websites
  - RTMP : used for Media Streaming

### Exam tips
- Edge Locations are not just READ only - you can write to them too
- Objects are cached for the life of the TTL
- You can clear cached objects but will be charged

## 3.16 CloudFront Lab

## 3.17 Snowball Overview
A petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data into and out of AWS.

50TB or 80TB size, tamper-resistant, chain-of-custody

Snowball Edge : 100TB data transfer device with on-board storage and compute capabilities

Snowmobile : an exabyte-scale data transfer device (100PB)

## 3.20 Snowball Lab

## 3.21 Storage Gateway
### Definition 
A service that connects an on-premises software appliance with cloud-based storage to provide seamless and secure integration between an organization's on-premises IT environment and AWS's storage infrastructure.
### 3 types of storage
- File Gateway (NFS&SMB) : files are stored as objects
- Volume Gateway (iSCSI) : disk volumes -> snapshot
  - stored volumes (1GB-16TB) : entire dataset is stored on site and is asynchronously backed up to S3
  - cached volumes (1GB-32TB) : entire dataset is stored on S3 and the most frequently accessed data is cached on site
- Tape Gateway (VTL, Virtual Tape Library) : archive data

## 3.22 Athena vs Macie
