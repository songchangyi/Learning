# EC2

## 4.1 EC2 101
A web service that provides resizable compute capacity in the cloud.

### Pricing models
1. On demand
  - low cost, flexibility, without up-front payment or long-term commitment
  - applications with short term, spiky or unpredictable workloads
  - being developped or tested on Amazon EC2 for the first time
2. Reserved (1 or 3 Yrs)
  - steady state or predictable usage
  - require reserved capacity
  - upfront payments to reduce the total costs
  1. Standard Reserved instances
  2. Convertible Reserved instances
  3. Scheduled Reserved instances
3. Spot
  - flexible start and end times
  - only feasable at very low compute prices
  - urgent computing needs for large amount of additional capacity
4. Dedicated Hosts (physical)
  - regulatory requirements that may not support multi-tenant virtualization
  - licensing which does not support multi-tenant or cloud deployments
  - can be purchased on-demand (hourly)
  - can be purchased as a reservation for up to 70% off the on-demand price
  
### EC2 Instances Types - Mnemonic
- F : FPGA
- I : IOPS
- G : Graphics
- H : High disk throughput
- T : Cheap general purpose
- D : Density
- R : RAM
- M : Main choice for general purpose apps
- C : Compute
- P : Graphics (Pics)
- X : Extreme memory
- Z : Extreme memory and CPU
- A : Arm-based workloads
- U : Bare metal

## 4.2 Let's Get Our Hands Dirty With EC2 - Part 1

## 4.3 Let's Get Our Hands Dirty With EC2 - Part 2
### Exam Tips
- Termination Protection is turned off by default
- On an EBS-backed instance, the default action is for the root EBS volume to be deleted when the instance is terminated
- EBS Root Volumes of your DEFAULT AMI's CAN be encrypted.
- Additional volumes can be encrypted

## 4.4 Security Groups Basics
### Exam Tips
- All inbound traffic is blocked by default
- All outbound traffic is allowed
- Changes take effict immediately
- Any number of EC2 instances within a security group
- Multiple security groups attached to EC2 instances
- Security Groups are stateful
- Create an inbound rule, that traffic is automatically allowed back out again
- Cannot block specific IP adresses using Security Groups, instead use Network Access Control Lists
- Can specify allow rules but not deny rules

## 4.5 EBS 101
### Definition
Elastic Block Store provides persistent block storage volumes for use with EC2 instances.
Each EBS volume is automatically replicated within its AZ to protect you from component failure, offering high availability and durability.

### 5 Different types
- General Purpose (SSD) : most work loads 16000
- Provisioned IOPS (SSD) : databases 64000
- Throughput Optimised Hard Disk Drive : big data & data warehouses 500
- Cold HDD : file services 250
- Magnetic : infrequently accessed 40-200

## 4.6 Volumes & Snapshots
