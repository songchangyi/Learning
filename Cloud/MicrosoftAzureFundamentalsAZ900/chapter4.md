# Core Cloud Services - Azure architecture and service guarantees

## Introduction
- Explore the physical structure of Azure infrastructure
- Understand the service level agreements provided by Azure
- Learn how to provide service level agreements for your apps

## Understand Datacenters and Regions in Azure

### What is a region?
A region is a geographical area on the planet containing at least one, 
but potentially multiple datacenters that are nearby and networked together with a low-latency network. 
Azure intelligently assigns and controls the resources within each region to ensure workloads are appropriately balanced.

This gives you the flexibility to bring applications closer to your users no matter where they are. 
It also provides better scalability, redundancy, and preserves data residency for your services.

### Special Azure regions
- US DoD Central, US Gov Virginia, US Gov Iowa and more: 
These are physical and logical network-isolated instances of Azure for US government agencies and partners. 
These datacenters are operated by screened US persons and include additional compliance certifications.
- China East, China North and more: These regions are available through a unique partnership between Microsoft and 21Vianet, 
whereby Microsoft does not directly maintain the datacenters.

## Understand Geographies in Azure
An Azure geography is a discrete market typically containing two or more regions that preserve data residency and compliance boundaries. This division has several benefits.

- Geographies allow customers with specific data residency and compliance needs to keep their data and applications close.
- Geographies ensure that data residency, sovereignty, compliance, and resiliency requirements are honored within geographical boundaries.
- Geographies are fault-tolerant to withstand complete region failure through their connection to dedicated high-capacity networking infrastructure.

Geographies are broken up into the following areas:
- Americas
- Europe
- Asia Pacific
- Middle East and Africa

## Understand Availability Zones in Azure
Availability Zones are physically separate datacenters within an Azure region.

Each Availability Zone is made up of one or more datacenters equipped with independent power, cooling, and networking. It is set up to be an isolation boundary. If one zone goes down, the other continues working. Availability Zones are connected through high-speed, private fiber-optic networks.

Not every region has support for Availability Zones.

## Understand Region Pairs in Azure
Availability zones are created using one or more datacenters, and there is a minimum of three zones within a single region. However, it's possible that a large enough disaster could cause an outage large enough to affect even two datacenters. That's why Azure also creates region pairs.

## Understand Service-Level Agreements for Azure
Formal documents called Service-Level Agreements (SLAs) capture the specific terms that define the performance standards that apply to Azure.

- SLAs describe Microsoft's commitment to providing Azure customers with specific performance standards.
- There are SLAs for individual Azure products and services.
- SLAs also specify what happens if a service or product fails to perform to a governing SLA's specification.

## SLAs for Azure products and services
There are three key characteristics of SLAs for Azure products and services:
- Performance Targets
- Uptime and Connectivity Guarantees
- Service credits

## Compose SLAs across services
When combining SLAs across different service offerings, the resultant SLA is called a Composite SLA. The resulting composite SLA can provide higher or lower uptime values, depending on your application architecture.

99.95 percent × 99.99 percent = 99.94 percent

Conversely, you can improve the composite SLA by creating independent fallback paths. For example, if the SQL Database is unavailable, you can put transactions into a queue for processing at a later time.

## Improve your app reliability in Azure
You can use SLAs to evaluate how your Azure solutions meet business requirements and the needs of your clients and users. By creating your own SLAs, you can set performance targets to suit your specific Azure application. This approach is known as an Application SLA.
