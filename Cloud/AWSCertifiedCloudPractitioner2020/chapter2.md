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
