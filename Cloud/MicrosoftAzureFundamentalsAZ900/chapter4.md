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
