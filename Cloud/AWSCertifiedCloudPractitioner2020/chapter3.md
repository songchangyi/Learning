# Chapter 3 Billing & Pricing

## 3.2 AWS Pricing 101
### The AWS Pricing White Paper
https://d0.awsstatic.com/whitepapers/aws_pricing_overview.pdf

### Capex vs Opex
- Capex : Capital Expenditure
- Opex : Operational Expenditure

### Pricing Policies
- Pay as you go
- Pay less when you reserve
- Pay even less per unit by using more
- Pay even less as AWS grows
- Custom pricing

### The Fundamentals Of Pricing
- Compute
- Storage
- Data Outbound

### Pricing models
- On Demand
- Dedicated Instances
- Spot Instances
- Reservations

### Free Services
- Amazon VPC (Virtual Private Cloud)
- Elastic Beanstalk
- CloudFormation
- IAM
- Auto Scaling
- Opsworks
- Consolidated Billing

### EC2 Pricing
- Hours of server time
- Instance type
- Pricing model
- Number of instances
- Load balancing
- Detailed monitoring
- Auto scaling
- Elastic IP Addresses
- OS and software packages

### Lambda Pricing
- Request pricing
  - Free tier : 1 million requests per month
  - $0.2 per 1 million requests thereafter
- Duration pricing
  - 400000 GB - seconds per month free (3.2 million seconds)
  - $0.00001667 for every GB - second used thereafter
- Additional charges

### EBS (Elastic Block Store)
- Volumes (per GB)
- Snapshots (per GB)
- Data transfer

### S3 Pricing
- Storage class
- Storage
- Requests (GET, PUT, COPY)
- Data transfer

### Glacier Pricing
- Storage
- Data retrieval times

### Snowball Pricing
PB-scale data transport solution.

- Service fee per job
- Daily charge
- Data Transfer

### RDS
- clock hours of server time
- DB characteristics
- DB perchase type
- number of DB instances
- provisioned storage
- additional storage
- requests
- deployment type
- data transfer

### DynamoDB

### CloudFront
- Traffic Distribution
- Requests
- Data Transfer Out

## 3.2 AWS Budgets vs Cost Explorer
### AWS Budgets
Set custom budgets that alert you when your costs or usage exceed your budgeted amount. Used to budget costs BEFORE they have been incurred.

### Cost Explorer
Visualize, understand and manage AWS costs AFTER they have been incurred.

## 3.3 Different Support Levels
### TAM (technical account manager)
- Enterprise !

## 3.4 Resource Groups & Tagging
### Tags
- KV pairs attached to AWS resources
- Metadata
- Can sometimes be inherited

You can group resources that share one or more tags. Resources groups contain informations such as :
- Region
- Name
- Employee ID
- Departement

Specific information : 
- EC2 : public & private IP addresses
- ELB : port configurations
- RDS : DB engineer

## 3.5 Consolidated Billing
### AWS Organizations
An account management service that enables you to consolidate multiple AWS accounts into an organization that you create and centrailly manage.

Available in two feature sets :
- Consolidated billing
- All features

Root->OU->AWS Account

### Consolidated Billing
- Paying account is independent. Cannot access resources of the other accounts.
- All linked accounts are independent
- Currently a limit of 20 linked accounts for consolidated billing

### Advantages
- One bill per AWS account
- Easy to track charges and allocate costs
- Volume pricing discount

### Best Practices
- Always enable multi-factor authentication on root account
- Always use a strong and complex password on root account
- Paying account should be used for billing purposes only

### CloudTrail
#### CloudTrail vs CloudWatch
- CloudWatch monitors performance
- CloudTrail monitors API calls in the AWS platform

#### To use CloudTrail
- Per AWS Account and is enabled per region
- Consolidate logs using S3 bucket
  1. Turn on CloudTrail in paying account
  2. Create a bucket policy that allows cross-account access
  3. Turn on CloudTrail in the other accounts and use the bucket in the paying account
  
  ## 3.6 AWS Organizations
