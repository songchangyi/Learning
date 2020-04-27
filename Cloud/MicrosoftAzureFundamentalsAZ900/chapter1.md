# Cloud Concepts - Principles of cloud computing

## What is cloud computing?
Cloud computing is renting resources, like storage space or CPU cycles, on another company's computers. 
You only pay for what you use. The company providing these services is referred to as a cloud provider. 
Some example providers are Microsoft, Amazon, and Google.

### Cloud computing services
#### Compute power
VMs aren't the only computing choice - there are two other popular options: 
containers and serverless computing.
- Containers

Containers provide a consistent, isolated execution environment for applications. 
They're similar to VMs except they don't require a guest operating system.

The open-source project, Docker, is one of the leading platforms for managing containers.

- Serverless computing

Serverless computing lets you run application code without creating, 
configuring, or maintaining a server. 
The core idea is that your application is broken into separate functions that run when triggered 
by some action.

#### Storage
The advantage to using cloud-based data storage is you can scale to meet your needs.

> Summary

> Every business has different needs and requirements. 
Cloud computing is flexible and cost-efficient, which can be beneficial to every business, 
whether it's a small start-up or a large enterprise.

## Benefits of cloud computing

### It's cost-effective
Cloud computing provides a pay-as-you-go or consumption-based pricing model.

### It's scalable
#### Vertical scaling
adding resources to increase the power of an existing server
#### Horizontal scaling
adding more servers that function together as one unit

### It's elastic
As your workload changes due to a spike or drop in demand, a cloud computing system can compensate by automatically adding or removing resources.

### It's current
Cloud usage eliminates the burdens of maintaining software patches, hardware setup, upgrades, and other IT management tasks.
 
### It's reliable
Cloud computing providers offer data backup, disaster recovery, and data replication services to make sure your data is always safe.

### It's global
Cloud providers have fully redundant datacenters located in various regions all over the globe.

### It's secure
Cloud providers offer a broad set of policies, technologies, controls, and expert technical skills that can provide better security than most organizations can otherwise achieve.

> Summary

> Cloud computing makes running a business easier. It's cost-effective, scalable, elastic, current, reliable, and secure. This means you're able to spend more time on what matters and less time managing the underlying details.

## Compliance terms and requirements

## Economies of scale

## Capital expenditure (CapEx) versus operational expenditure (OpEx)

### Benefits of CapEx
With capital expenditures, you plan your expenses at the start of a project or budget period. Your costs are fixed, meaning you know exactly how much is being spent.

### Benefits of OpEx
OpEx is particularly appealing if the demand fluctuates or is unknown. Cloud services are often said to be agile.

## Cloud deployment models

### Public cloud
Advantages
- High scalability/agility – you don't have to buy a new server in order to scale
- Pay-as-you-go pricing – you pay only for what you use, no CapEx costs
- You're not responsible for maintenance or updates of the hardware
- Minimal technical knowledge to set up and use - you can leverage the skills and expertise of the cloud provider to ensure workloads are secure, safe, and highly available

Disadvantages
- There may be specific security requirements that cannot be met by using public cloud
- There may be government policies, industry standards, or legal requirements which public clouds cannot meet
- You don't own the hardware or services and cannot manage them as you may want to
- Unique business requirements, such as having to maintain a legacy application might be hard to meet

### Private cloud
Advantages
- You can ensure the configuration can support any scenario or legacy application
- You have control (and responsibility) over security
- Private clouds can meet strict security, compliance, or legal requirements

Disadvantages
- You have some initial CapEx costs and must purchase the hardware for startup and maintenance
- Owning the equipment limits the agility - to scale you must buy, install, and setup new hardware
- Private clouds require IT skills and expertise that's hard to come by

### Hybrid cloud
Advantages
- You can keep any systems running and accessible that use out-of-date hardware or an out-of-date operating system
- You have flexibility with what you run locally versus in the cloud
- You can take advantage of economies of scale from public cloud providers for services and resources where it's cheaper, and then supplement with your own equipment when it's not
- You can use your own equipment to meet security, compliance, or legacy scenarios where you need to completely control the environment

Disadvantages
- It can be more expensive than selecting one deployment model since it involves some CapEx cost up front
- It can be more complicated to set up and manage

## Types of cloud services
- Infrastructure as a service (IaaS)
> When using IaaS, ensuring that a service is up and running is a shared responsibility: the cloud provider is responsible for ensuring the cloud infrastructure is functioning correctly; the cloud customer is responsible for ensuring the service they are using is configured correctly, is up to date, and is available to their customers. This is referred to as the shared responsibility model.

- Platform as a service (PaaS)
- Software as a service (SaaS)
