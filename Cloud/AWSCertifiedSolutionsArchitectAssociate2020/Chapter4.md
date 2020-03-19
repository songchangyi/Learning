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
