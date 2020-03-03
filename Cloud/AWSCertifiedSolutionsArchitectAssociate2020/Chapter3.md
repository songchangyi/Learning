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

