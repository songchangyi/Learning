# Core Cloud Services - Azure compute options

## Essential Azure compute concepts

### What is Azure compute?
Azure compute is an on-demand computing service for running cloud-based applications.

There are four common techniques for performing compute in Azure:
- Virtual machines
- Containers
- Azure App Service
- Serverless computing

### What are virtual machines?
Virtual machines, or VMs, are software emulations of physical computers.

### What are containers?
Just like virtual machines, containers are run on top of a host operating system. 
But unlike VMs, containers don't include an operating system for the apps running inside the container. 
Instead, containers bundle the libraries and components needed to run the application and 
use the existing host OS running the container.

### What is Azure App Service?
Azure App Service is a platform-as-a-service (PaaS) offering in Azure that is designed to 
host enterprise-grade web-oriented applications.

### What is Serverless Computing?
Serverless computing is a cloud-hosted execution environment that runs your code 
but completely abstracts the underlying hosting environment.

## Explore Azure Virtual Machines
Azure Virtual Machines (VMs) let you create and use virtual machines in the cloud. 
They provide infrastructure as a service (IaaS) in the form of a virtualized server and 
can be used in many ways. Just like a physical computer, 
you can customize all of the software running on the VM. VMs are an ideal choice when you need:
- Total control over the operating system (OS)
- The ability to run custom software, or
- To use custom hosting configurations

### What are availability sets?
An availability set is a logical grouping of two or more VMs that help keep your 
application available during planned or unplanned maintenance.
- Update domains are a logical part of each data center and are implemented with software and logic.
- A fault domain is essentially a rack of servers.

There's no cost for an availability set. 
You only pay for the VMs within the availability set. 
We highly recommend that you place each workload in an availability set to avoid having a 
single point of failure in your VM architecture.

### What are virtual machine scale sets?
Scale sets allow you to centrally manage, configure, 
and update a large number of VMs in minutes to provide highly available applications.

### What is Azure Batch?
Azure Batch enables large-scale job scheduling and compute management with the 
ability to scale to tens, hundreds, or thousands of VMs.

### Explore Containers in Azure
If you wish to run multiple instances of an application on a single host machine, containers are an excellent choice. 
The container orchestrator can start, stop, and scale out application instances as needed.

### Containers in Azure
- Azure Container Instances (ACI)
- Azure Kubernetes Service (AKS)

#### Azure Container Instances
Azure Container Instances (ACI) offers the fastest and simplest way to run a container in Azure. 
You don't have to manage any virtual machines or configure any additional services. 
It is a PaaS offering that allows you to upload your containers and 
execute them directly with automatic elastic scale.

#### Azure Kubernetes Service
The task of automating, managing, and interacting with a large number of containers is known as 
orchestration. Azure Kubernetes Service (AKS) is a complete orchestration service for containers 
with distributed architectures with multiple containers.

### Migrating apps to containers
The preceding figure depicts this process as follows:
1. You convert an existing application to one or more containers and then publish one or more container images to the Azure Container Registry.
2. By using the Azure portal or the command line, you deploy the containers to an AKS cluster.
3. Azure AD controls access to AKS resources.
4. You access SLA-backed Azure services, such as Azure Database for MySQL, via OSBA.
5. Optionally, AKS is deployed with a virtual network.

## Explore Azure App Service
Azure App Service enables you to build and host web apps, background jobs, mobile backends, 
and RESTful APIs in the programming language of your choice without managing infrastructure. 
It offers automatic scaling and high availability. App Service supports both Windows and Linux, 
and enables automated deployments from GitHub, Azure DevOps, 
or any Git repo to support a continuous deployment model.

### Types of web apps
With Azure App Service, you can host most common web app styles including:
- Web Apps
- API Apps
- WebJobs
- Mobile Apps

## Explore Serverless computing in Azure
Serverless computing is the abstraction of servers, infrastructure, and OSs. 
With serverless computing, Azure takes care of managing the server infrastructure and 
allocation/deallocation of resources based on demand. Infrastructure isn't your responsibility. 
Scaling and performance are handled automatically, and you are billed only for the exact resources 
you use. There's no need to even reserve capacity.

Serverless computing encompasses three ideas: 
the abstraction of servers, an event-driven scale, and micro-billing

Azure has two implementations of serverless compute:
- Azure Functions, which can execute code in almost any modern language.
- Azure Logic Apps, which are designed in a web-based designer and can execute logic triggered by 
Azure services without writing any code.
