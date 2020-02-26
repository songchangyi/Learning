# Security In The Cloud

## 4.1 AWS Compliance & AWS Artifact

## 4.2 Shared Responsibility Model
https://aws.amazon.com/compliance/shared-responsibility-model/

AWS is responsible for security of the cloud : (which you can not do this in the console)
- Hardware / AWS global infrastructure : regions, AZ, Edge locations
- Software : Compute, Storage, Database, Networking

Customer is responsible for security in the cloud : 
- Data
- Platform, Apps, IAM
- OS, Netwok and firewall
- client side data, server-side data, networking traffic

## 4.3 AWS WAF & AWS Shield
WAF is a web application firewall that helps protect your web applications from common web exploits.

AWS Shield is a managed DDoS (Distributed Denial of Service) protection service.

### Exam Tips
- AWS WAF is a Web application Firewall designed to stop hackers.
- AWS Shield is a DDOS mitigation service designed to stop DDOS attacks.

## 4.4 AWS Inspector vs AWS Trusted Advisor vs CloudTrail
### AWS Inspector
Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS.

### AWS Trusted Advisor
Advise you on cost optimisation, performance, security, fault tolerance.
- Core checks and recommendations.
- Full Trusted Advisor

### CloudTrail
Monitor APIs calls from the platform.

### Exam Tips
- AWS Inspector is used for inspecting EC2 instances for vulnerabilities.
- AWS Trusted advisor inspects your AWS account as a whole.
- AWS CloudTrail, record console actions and API calls.

## 4.5 CloudWatch vs AWS Config
### CloudWatch
CloudWatch is a monitoring service to monitor your AWS resources and applications.

### Host level metrics consist of
- CPU
- Network
- Disk
- Status check

### AWS Config
AWS Config provides a detailed view of the configuration of AWS resources in your AWS account.

### Exam Tips
- CloudWatch is used for monitoring performance.
- AWS Config is used to monitor configurations of your AWS resources.

## 4.6 Athena Vs Macie
### Athena
Interactive query service which enables you to analyse and query data located in S3 using standard SQL.
- Serverless
- No need to set up ETL processes
- Works directly with data stored in S3

### Athena use cases
- query log files stored in S3
- generate business reports on data stored in S3
- analyse AWS cost and usage reports
- run queries on click-stream data

### Macie
PII : personally identifiable information

Macie is a security service which uses Machine Leaning and NLP to discover and protect sensitive data stored in S3.

## 4.7 Security Summary
