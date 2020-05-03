# Core Cloud Services - Azure networking options

## Deploy your site to Azure

### Using an N-tier architecture
Three-tier refers to an n-tier application that has three tiers. 
Your e-commerce web application follows this three-tier architecture:
- The web tier provides the web interface to your users through a browser.
- The application tier runs business logic.
- The data tier includes databases and other storage that hold product information and customer orders.

### What's a network security group?
A network security group, or NSG, allows or denies inbound network traffic to your Azure resources.

## Scale with Azure Load Balancer

### What are availability and high availability?
Availability refers to how long your service is up and running without interruption. 
High availability, or highly available, 
refers to a service that's up and running for a long period of time.

### What is resiliency?
Resiliency refers to a system's ability to stay operational during abnormal conditions.

### What is a load balancer?
A load balancer distributes traffic evenly among each system in a pool. 
A load balancer can help you achieve both high availability and resiliency.

### What is Azure Load Balancer?
Azure Load Balancer is a load balancer service that Microsoft provides that helps take care of the 
maintenance for you.

### Azure Application Gateway
If all your traffic is HTTP, a potentially better option is to use Azure Application Gateway.

### What is a Content Delivery Network?
A content delivery network (CDN) is a distributed network of servers that can efficiently 
deliver web content to users.

## Reduce latency with Azure Traffic Manager

### What is network latency?
Latency refers to the time it takes for data to travel over the network. 
Latency is typically measured in milliseconds.

### Scale out to different regions
How can you connect users to the service that's closest geographically, 
but under the contoso.com domain?

### Use Traffic Manager to route users to the closest endpoint
One answer is Azure Traffic Manager. 
Traffic Manager uses the DNS server that's closest to the user to direct user traffic to a globally 
distributed endpoint.

### Compare Load Balancer to Traffic Manager
- Azure Load Balancer distributes traffic within the same region to make your services more 
highly available and resilient. 
- Traffic Manager works at the DNS level, and directs the client to a preferred endpoint. 
This endpoint can be to the region that's closest to your user.
