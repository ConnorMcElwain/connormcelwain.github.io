---
title: "Azure AZ-900 Certification Notes"
date: 2024-04-10T10:21:50-05:00
description: "Test description"
author: "Connor McElwain"
draft: false
type: "post"
showTableOfContents: false 
tags: ["Azure", "AZ-900", "Cloud", "Notes"]
---

# Chapter 1 - Introduction
## PowerShell
- **Cmdlet** is a script that performs a specific task. "New-AzVm" creates a new Virtual Machine.
- **Azure Resource Manager** is utilized by PowerShell, like the Portal in Azure, to manipulate Azure resources.
- PowerShell is versatile, it's used for many other tasks and areas, not just for Azure.


## Cloud Shell
Cloud Shell is an interactive, browser-accessible shell for managing Azure resources. There's a stand-alone window version of the Azure Cloud Shell and an "In-Portal" integrated version as well. You can choose between both **Bash** and **PowerShell** shells. You can access this tool from anywhere using the web or mobile app. The Cloud Shell has **dedicated storage** to persist data between sessions.


## Accessing and Using the Azure Cloud Shell (Lab)
**Lab Tasks/Steps**
Azure CLI Commands
- az group list
- az storage account list
- az vm list
- az vm create

PowerShell Commands
- Get-AzResourceGroup
- Get-AzStorageAccount
- Get-AzVM
- Get-AzResource | ft
- Remove-AzVM

**[Lab Link](https://learn.acloud.guru/handson/c3b7cd51-ba36-4bdb-b815-0ea8b444a41f/course/az-900-microsoft-azure-fundamentals)**


## Azure Advisor
Azure Advisor is made to guide and inform the user of ways to save money, learn about features they may not know about, but can be helpful, and ensure settings and features are properly configured to ensure security, reliability, and saving money.


------


# Chapter 2 - Cloud Concepts
## The Language of Cloud Computing
### Terms
* High availability
	* Traditional:
		* You own the hardware
		* You have physical access
		* You can't "just add servers"
	* Cloud:
		* You don't own the hardware
		* Add more servers with a click
		* If hardware fails, replace it instantly
		* Use clusters to ensure high availability
* Scalability
	* Automatically adjust resources to meet demand
		* Example: Increase the number of VMs to handle peak traffic
	* Don't overpay for services
		* Automatically reduce resources when demand drops
	* Horizontal vs. Vertical Scaling
		* Horizontal = Adding additional VMs/containers
			* "Scaling out"
		* Vertical = Increasing power (e.g., CPU/RAM) of existing VMs
			* "Scaling up"
		* 'Typical' cloud model = Horizontal scaling
* Predictability
	* Predictable Performance and Costs
		* Performance
			* Consistent experience for customers regardless of traffic
			* Autoscaling, load balancing, and high availability provide a consistent experience
		* Costs
			* No unexpected surprises
			* Track and forecast resource usage (costs) in real time
			* Analytics provide patterns/trends to optimize usage
* Reliability
	* Resilience
		* The ability of a system to recover from failures and continue to function
	* Deploy in Multiple Locations
		* Global-scale computing
		* Protects against regional failure/disaster
	* No Single Point of Failure
		* Resources in multiple locations
		* If one computer goes down, others pick up the load
* Security
	* Full control of the security of your cloud environment. Patches, maintenance, network control, and more.
* Governance
	* Standardize environments
	* Regulatory requirements
	* Audit for compliance
* Manageability
	* Management of the cloud:
		* Autoscaling
		* Monitoring
		* Template-based deployments
	* Management in the cloud:
		* Portal
		* CLI
		* APIs

### Exam Tips
#### Cloud computing has terms that are specific and critical to understanding it
* High availability means systems are always available -- even automatically.
* Reliability describes how Azure can tolerate failures or even disasters.
* Scalability refers to scaling out or scaling up while automatically providing resources as needed.
* Predictability is knowing your application will always perform as expected and knowing what it will cost.
* Security is having full control of  your cloud security posture.
* Governance is standardizing cloud deployments to meet requirements/company standards.
* Manageability is management of cloud resources and how we interact with them.


## The Economy of Cloud Computing
### Capital and Operational Expenditure
* Capital Expenditure
	* Money spent by a business or organization on acquiring or maintaining fixed assets, such as land, buildings, and equipment.
	* Large upfront investments.
* Operational Expenditure
	* An ongoing cost for running a product, business, or system on a day-to-day basis, including annual costs.
	* Pay-as-you-go

* Consumption-based Pricing
	* Low usage = Low cost
		* No lock-in fees. Exposure to Azure.

### Exam Tips
* Capital Expenditure (CapEx) is buying hardware outright, paid upfront as a one time purchase.
* Operational Expenditure (OpEx) is ongoing costs needed to run your business.
* Consumption-based pricing let's you pay only for what you use.


## Cloud Service Models
### Infrastructure-as-a-Service (IaaS)
* Infrastructure = actual servers
* Scaling is fast
* No ownership of hardware
IaaS offers VMs & Servers, Storage, Networking components, firewall and the physical hardware everything runs on.

### Platform-as-a-Service (PaaS)
* Superset of IaaS
	* Offers all that IaaS
		* Also offers Middleware, development tools, business intelligent, services, database management systems, and more.
* PaaS supports web application life cycle
* Avoids software license hell

### Software-as-a-Service (SaaS)
* Providing a managed service
	* Provides all that PaaS and IaaS provides
		* Also offers apps/software
* Pay an access fee to use
* No maintenance and latest features

### Serverless
* There are servers, this just means you don't have to manage any servers. You are using someone else's servers
* Azure Functions is the best know serverless service
* Extreme PaaS

## Identifying Cloud Service Models
* IaaS
	* Organization has complete control of the infrastructure
	* Dynamic and flexible. You can do almost anything.
	* Cost varies depending on consumption
	* Services are highly scalable
	* Multiple users share a single piece of hardware
	* Examples:
		* VM
		* VNet
		* Storage
* PaaS
	* Resources are virtualized and can easily be scaled up or down as needed
	* Services often assist with the development, testing, and deployment of apps
	* Multi-user access via the same development application
	* Integrates web services and databases
	* Examples:
		* App Services
		* Azure CDN
		* Cosmos DB
* SaaS
	* Managed from a central location
	* Hosted on a remote server
	* Accessible over the internet
	* Users not responsible for hardware or software updates
	* Rate limiting/QoS
	* Examples:
		* Microsoft 365

### Exam Tips
Service is the core of Azure, and there are three main ways to go about it.
* IaaS provides servers, storage and networking as a service
* PaaS is a superset of IaaS and also includes middleware, such as database management tools
* SaaS is when service is built on top of PaaS, like Office 365
* Serverless means that you don't have any servers. Let's a single function be hosted, deployed, run and managed on its own


## Azure Marketplace
* Solutions and Services
	* Large selection from Microsoft and partners. Apps, VMs, templates, services and more
* Azure Apps Store
	* Buy cloud services with a single click. Many categories of items to acquire
* Easy to Integrate
	* Use from Portal, CLI or PowerShell. Some are free, some are paid


## Cloud Architect Models
* Private Cloud
	* Pros
		* Complete control of infrastructure
		* Benefits of public cloud
		* Better security and privacy
	* Cons
		* Maintenance
		* Staffing
* Public Cloud
	* Pros
		* No purchase of hardware
		* Low monthly fees
	* Cons
		* No control over features and versions
		* No physical access
* Hybrid Cloud
	* Pros
		* Avoid disruptions and outages
		* Adhere to regulation, governance etc.
		* Span both public and private cloud
		* Alleviate CapEx investments
	* Cons
		* Complex infrastructures

### Exam Tips
* Private cloud is Azure on your own hardware in a location of your choice. All the benefits of public cloud, but you can lock it down. A lot of staff required.
* Public cloud is Azure, AWS, GCP. No upfront costs, but monthly usage. Little control over services and infrastructure.
* A hybrid cloud model is the best of private and public, but could be complex.


## Chapter 2 Summary
### Cloud Concepts Summary
* Language of Cloud Computing
	* High availability, fault tolerance, disaster recovery, scalability, elasticity and agility. Describes stable and dependable cloud computing, the ability to adapt to changes in resource demand, user base and application usage.
* Language of Cloud Economics
	* CapEx and OpEx describe costs for computing. OpEx is cloud computing with a pay-as-you-go model.
* Cloud Service Models
	* IaaS, PaaS, and SaaS are cloud service models that pretty much all Azure products and services fall under.
	* The shared responsibility model dictates whether you or Microsoft is responsible for a cloud service.
* Azure Marketplace
	* An extra layer of functionality for your cloud applications, by letting users use and integrate third-party products and services.
* Cloud Architecture Models
	* Private, public, and hybrid approaches to using cloud computing for your business.

------

# Chapter 3 - Azure Architecture
## Regions & Availability Zones
### Region Definition
"A region is a set of datacenters deployed within a latency-defined perimeter and connected through a dedicated regional low-latency network."

### Region Definition - Broken Down
* A set datacenters
	* Each region has more than one data center, which is a physical location.
* Latency defined perimeter
	* Latency is the time it takes data to travel. Also means that datacenters are not "too far" from each other.
* Regional low-latency network
	* A fiber connection between data centers in the region.

Two or more data centers not too far from each other connected with a fiber connection.

### How to Choose a Region
* Location
	* Choose a region closest to your users to minimize latency.
* Features
	* Some features aren't in all regions. If you need a specific feature, some regions might be unavailable.
* Price
	* The price of services vary from region to region.

You will often have to choose which is the most important: location, feature, or price.

### Paired Region
* Each Region is Paired
	* Paired within same geographic are except Brazil South.
* Outage Failover
	* If the primary region has an outage, you can failover to the secondary region.
* Planned Updates
	* Only one region in a pair is updated at any one time.
* Replication
	* Some services used paired regions for replication.

### Availability Zones
* Physical Location
	* Each availability zone is a physical location within a region.
* Independent
	* Each zone has its own power, cooling and networking.
* Zones
	* Each region has a minimum of three zones.

#### Summary
* Azure Region
	* A set of data centers that are close enough to each other that it doesn't matter which datacenter you data is in. Latency is the time it takes for data to travel.
* Availability Zone
	* Within a region and each zone has its own separate power, cooling and networking. Used for protecting data from failures.


## Resource Groups & Azure Resource Manager
### Resource Groups
Everything in Azure is inside a resource group, no exceptions! While all resources must be inside of a resource group, the resource groups themselves are not a resource.

### Resource Group Facts
* One Resource
	* Each resource can only exist in a single resource group.
* Add/Remove
	* You can add or remove resources to any resource group at any time.
* Move Resource
	* You can move a resource from one resource group to another.
* Multiple Regions
	* Resources from multiple regions can be in one resource group.
* Access Control
	* You can give users access to a resource group and everything in it.
* Interact
	* Resources can interact with other resources in different resource groups.
* Location
	* A resource group has a location, or region, as it stores meta data about the resources in it.

### Azure Resource Manager (ARM)
This is deployment and management services for Azure. If you interact with any of the resources on Azure, it goes through ARM.

### ARM Benefits
* Group Resource Handling
	* You can deploy, manage, and monitor resources as a group.
* Consistency
	* Deploying resources from various tools will always result in the same consistent state.
* Dependencies
	* Define dependencies between resources to make sure they don't get in a fight.
* Access Control
	* Built-in features in the ARM make it easy to assign access rights to users.
* Tagging
	* Tag resources to easily identify them for future scenarios. Tagging is a way to label individual resources.
* Billing
	* Use tagging to stay on top of billing for groups of resources.

#### Summary
* Resource Groups
	* All resources belong to a resource group. It isn't a resource, but helps structure your Azure architecture.
* Azure Resource Manager
	* All interaction with Azure resources go through the ARM. It's the main Azure Architecture component for creating, updating, and manipulating resources.


------


# Chapter 4 - Compute
## Virtual Machines
### What is a Virtual Machine?
A virtual machine is the virtualization or emulation of a computer system. They are based on computer architectures and provide the same functionality as a physical machine.

### Features
* Infrastructure-as-a-Service (IaaS)
	* Manage everything except the hardware. This includes the network components
* Tools
	* Use the Azure Portal to manage large numbers of VMs and even hybrid clouds
* Compliance
	* Use Azure blueprints to make your VMs comply with company guidelines
* Recommendations
	* Azure will recommend improvements to ensure better security, higher availability, and greater performance
* Choice
	* Choose amount of RAM, number of CPUs, Windows or Linux

### Pricing
* Calculated Hourly
	* The more CPUs, GPUs, and amount of RAM you want, the more you pay per hour

### Use Cases
* Pros:
	* Control
		* Use virtual machines when you need to control all aspects of an environment or machine
	* Application
		* Install specific applications on your Windows or Linux machines
	* Existing Infrastructure
		* You can move existing resources and virtual machines to Azure from on-premises or another cloud provider
* Cons:
	* Not for Everything
		* If you can use another Azure service instead, it is often worth it
	* Maintenance
		* A lot of maintenance with VMs. Operating system updates, patches, security concerns

### Exam Tips
Virtual Machines are at the core of Azure compute and are widely used.
* A virtual machine is  your machine exclusively
* You don't buy, own or control any hardware. Azure does this
* Virtual machines are an IaaS offering where you are responsible for the entire machine
* Azure virtual machines take advantage of Azure tools
* Pricing goes up as resources go up, and you pay by the hour


## Scale Sets
### Definition
A group of identical, load balanced VMs.

### Benefits
* Multiple VMs
	* Simple to manage multiple identical VMs using a load balancer
* High Availability
	* If one VM fails or stops, the others in the scale set will keep working
* Auto Scaling
	* Automatically match demand by adding or removing VMs from the scale set
* Large Scale
	* Run up to 1000 VMs in a single scale set
* No Extra Cost
	* No added cost for using scale sets

### Exam Tips
Scale sets are taking virtual machines to the next level. And keeping your sanity.
* Scale sets are identical VMs. They can be activated or deactivated as needed
* A baseline VM for the scale set ensures application stability. A baseline VM is what you copy to make up the scale set VMs
* As resource usage increases, more VMs are activated to take the load
* You only pay for the VM, storage, and networking resources you use. Nothing additional for scale sets


## App Services
App Services are a fully managed platform. The servers, networks, and storage are all handled and managed by Azure. The only thing you have to do is focus on business value and logic.

* App Services
	* Web Apps
		* Website and online applications hosted on Azure's managed platform
			* Runs on both Windows and Linux platforms
			* Supports a lot of languages, such as .NET, Java, Node.js, PHP, Python, and Ruby
			* Azure integration for easier deployment
			* Auto-scaling and load balancing
	* Web Apps for Containers
		* Deploy and run containerized applications in Azure
			* A container is completely self-contained
			* All dependencies are shipped inside the container
			* Deploy anywhere with a consistent experience
			* Reliable between environments
	* API Apps
		* Expose and connect your data backend
			* Application Programming Interface
			* No graphical component. No user interface
			* Connect other application programmatically
			* Use a range of programming languages

### Exam Tips
App services is an easy way to host and manage your web applications.
* App services are a PaaS offering on Azure
* Web Apps are used to host web sites and web applications
* Web Apps for Containers can host your existing container images
* API Apps can host your data backend services


## Azure Container Instances
### Features
* Manage Application Dependencies
	* All the dependencies for an application are included in the container image. You can manage the application and its dependencies with confidence
* Less Overhead
	* Virtual machines require a lot more maintenance and updates. Containers don't have any components relating to the operating system that require maintenance
* Increased Portability
	* Applications running in containers can be deployed easily to multiple different operating systems and hardware platforms
* Efficiency
	* Development, deployment, and maintenance are all more efficient when using containers. Scaling and patching is much simpler
* Consistency
	* The operations team can rely on containers being the same every time, no matter which target they are being deployed to

### Workflow
* Software Development Cycle
* Application placed in a container
* Azure Container Instances

### Azure Container Instances
* User to Run Container Workloads
	* Primary Azure service for running container workloads. A workload is your process or application
* On Demand = Save money
	* Use containerized applications to process data on demand, by only creating the container image when  you need it. Saving some money in the process
* Works With Your Tool of Choice
	* Use the Azure Portal, Azure CLI, or PowerShell. Whichever you like the most


## Azure Kubernetes Service
Kubernetes is an open-source container orchestration system for automating application deployment, scaling, and management.

* Open Source
	* Public code base and community involvement in the product
* Orchestration
	* Keeps track of lots of parts of a system. Makes sure containers are configured correctly to work together
* Automatic application deployment
	* Kubernetes will deploy more images of containers as needed
* Automatic scaling
	* Automatic monitoring of application load to determine when to scale the number of containers used

### Azure Kubernetes Service
* Replicate Container Architectures
	* Reuse your container architecture by managing it in Kubernetes. This makes your setup quicker and confidence in the system increase
* Standard Azure Services Included
	* You don't have to worry about infrastructure and hardware. Get identity and access management, elastic provisioning and much more
* Global Reach
	* Use Kubernetes with supported Azure regions and on-premises installations using Azure Stack

### Azure Container Registry (ACR)
* Keeps track of current valid container images
* Manages files and artifacts for containers
* Feeds container images to ACI and AKS
* Use Azure identity and security features


## Azure Virtual Desktop
Use any VM you want and access it from any device that has web access and a modern web client.

### Benefits
Azure Virtual Desktop is a completely virtualized version of Windows, meaning it runs 100% in the cloud.
* Reuse Windows 10 Licenses
	* This will reduce costs and streamline license usage
* Concurrency
	* Multiple users can use the same VM instance
* Access Anywhere
	* Use Windows 10/11 from anywhere on any device with an internet browser
* Secure Data
	* Use Azure Storage to secure your data


## Functions
### What are Azure Functions?
* IaaS/PaaS vs Function
	* IaaS/PaaS
		* Install your own applications
		* Access to the operating system
		* Resource visibility
		* An app service has no OS access, but has resource access
	* Function
		* Smallest compute service on Azure
		* A single function of compute
		* Called, or invoked, via a standard web address
		* Runs once and stops

### Architecture
* VM
	* No maintenance
	* No processes
	* Nothing VM related

### Function Benefits 
* Only Runs When Needed
	* The Azure Function only runs when there is data to process. No traffic = no resource usage
* Saves Money
	* No resources running means you don't pay for the function when it's not used
* Resilience
	* If your function fails, it doesn't affect other function instances


## Chapter 4 Summary
* Virtual Machines
	* Virtualized hardware you control. Spin up ad down as needed. Take advantage of the Azure tools available. Priced per hour with many configurations available.
* Scale Sets
	* Sets of identical VMs. Scale sets automatically create and delete VMs for your application. Provides high availability and protects against server failures
* App Services
	* Managed platform to host your applications. Web app, containers and API. Supports a lot of programming languages
* Azure Container Instances
	* Hosts and runs your containers on Azure. Containers have less overhead than virtual machines and can be deployed consistently
* Azure Kubernetes Service
	* Open-source tool for orchestrating and managing many container images and applications. Uses clusters and pods to scale and deploy applications
* Windows Virtual Desktop
	* 100% virtualized Windows 10. Access with any device that has a browser and internet connection. Reuse licenses to save some money
* Functions
	* Serverless Azure offering. A function does one compute action each time it's invoked


------


# Chapter 5 - Networking
## Virtual Network
A virtual network (VNet) enables many types of Azure resources, such as Azure virtual machines, or VMs, to securely communicate with each other, the internet, and on-premises networks. A virtual network is virtual because, while you get access to it, you don't have any access to the hardware. Just like a virtual machine, it's yours to use, but the physical hardware is hidden away.

### Address Space
An address space is the range of IP addresses that are available. Every service or resource that is connected to a VNet will get its own unique address on that VNet within the address space. That's how services on the same VNet can find each other and communicate.

### Subnets
* Resource Grouping
	* Group resources onto the same subnet to make it easier to keep an overview
* Address Allocation
	* More efficient to allocate addresses to resources on a smaller subnet
* Subnet Security
	* Use network security groups to secure individual subnets

### Subnet Regions & Subscriptions
* Regions
	* A VNet belongs to a single region. Every resource on the VNet must be in the same region too
* Subscriptions
	* A VNet belongs to just one subscription, but a subscription can have multiple VNets

### Cloud Advantages
* Scaling
	* Adding more VNets or more addresses to one is simple
* High Availability
	* Peering VNets, using a load balancer, or using VPN gateway all increase availability
* Isolation
	* Manage and organize resources with subnets and network security groups

### VNet Peering
This feature lets you connect 2 or more virtual networks in Azure. Traffic between virtual machines in a peered network uses the private Microsoft backbone network and never passes through the public internet. Just like if the VMs were on the same virtual network.

### Peering Benefits
* Low Latency, High Bandwidth
	* Resources in virtual networks are connected with a low-latency, high-bandwidth connection
* Link Separate Networks
	* Resources in separate virtual networks can communicate with each other
* Data Transfer
	* Transfer data easily between subscriptions and deployment models in separate regions

### Exam Tips
A virtual network is a fundamental part of your Azure infrastructure.
* An address space is range of IP addresses you can use for your resources
* A subnet is a smaller network, which is part of your VNet. Use these for security and logical division of resources
* A VNet is in a single region and single subscription
* VNets in the cloud can scale, have high availability and isolation


## Load Balancer
### Load Balancer Description
Load Balancer distributes new inbound flows that arrive on the Load Balancer's frontend to backend pool instances, according to rules and health probes.
* Inbound Flows
	* Traffic from the internet or local network
* Frontend
	* The access point for the load balancer. All traffic goes here first
* Backend Pool
	* The VM instances receiving traffic
* Rules & Health Probes
	* Checks to ensure backend instance can receive the data

### Scenarios
* Internet Traffic
	* Balanced the load of incoming internet traffic into a system application
* Internal Networks
	* A load balancer works well with internal applications
* Port Forwarding
	* Traffic can be forwarded to a specific machine in the backend pool
* Outbound Traffic
	* Allow outbound connectivity for backend pool VMs


## VPN Gateway
### Virtual Network Gateway
A virtual network gateway is composed of two or more virtual machines that've been deployed to a specific subnet you create, which is called the gateway subnet.

### VPN Gateway
A VPN Gateway is a specific type of virtual network gateway that is used to send encrypted traffic between an Azure virtual network and an on-premises location over the public internet.

### Exam Tips
VPN Gateways are instrumental in a hybrid cloud architecture.
* A VPN Gateway is a specific VNet Gateway. It consists of two or more dedicated VMs
* VNet Gateway + "vpn" becomes a VPN Gateway
* Sends encrypted data between Azure and on premises network
* Azure Gateway Subnets, secure tunnel and on-premises gateway makes up a VPN Gateway scenario


## Application Gateway
### Benefits
* Scaling
	* Scale the Application Gateway up or down based on the amount of traffic received
* Encryption
	* Comply with any security policies. Disable or enable traffic encryption to the backend
* Zone Redundancy
	* Span multiple availability zones and improve fault resiliency
* Multi-site Hosting
	* Use the same application gateway for up to 100 websites

### Exam Tips
An application gateway is a higher level load balancer.
* It works on the HTTP request of the traffic, instead of the IP address and port
* Traffic from a specific web address can go to a specific machine
* Is a fit for most other Azure services
* Supports auto-scaling, end-to-end encryption, zone redundancy, and multi-site hosting


## Content Delivery Network
Content Delivery Network = CND. It is a distributed network of servers that can deliver web content close to users.

### Benefits
* Better Performance
	* Improve the user experience and the performance of your application
* Scaling
	* Scale to suit any spikes in traffic, and also protect your main backend server instance from high loads
* Distribution
	* Edge servers will serve requests closest to the user. Less traffic is then sent to the server hosting your application

### Terminology
* Cache
	* Collection of temporary copies of original files. The primary purpose is to optimize speed for an application. When a copy expires, a new copy is needed
* Origin Server
	* The original location of the files, such as a web application. It's the master copy of your application


## ExpressRoute
If you need a private, secure, high-bandwidth, low-latency connection, directly from your data center or infrastructure to Azure, ExpressRoute is the service you want to use.


## Chapter 5 Summary
### Networking Summary
* Virtual Network
	* A fundamental part of Azure. All services are connected to a VNet. Includes an IP address range and subnets. Belongs to a single region and a single subscription
* Load Balancer
	* Distributes and balances the incoming traffic to an application or network. Uses IP address and port number to determine the receiving VM in the backend pool
* VPN Gateway
	* Connects your Azure network with your on-premises network securely
* Application Gateway
	* Distributes incoming traffic based on HTTP request properties, such as URL and host headers. Same session traffic can be handled by multiple servers
* ExpressRoute
	* Direct link between on-premises and Azure . Enables a private, secure, high-bandwidth, low-latency connection
* Content Delivery Network
	* Stores a cached version of your application on an edge node. Provides better performance and less traffic to your main server. Content cache is updated as necessary


------


# Chapter 6 Storage
## Blob
Blob means "Binary Large Object"

### Storage Levels
These blobs of data are stored in containers, inside the storage account. There are three layers to Blob storage: storage account, container, and then blob.

### Scenarios
* Images
	* Store various sizes and formats as a single image storage
* All Types
	* Store any kind of files and have distributed access through the Azure cloud storage
* Streaming
	* Stream audio and video directly from your blob storage
* Log files
	* Write to log files regardless of size and frequency
* Data Store
	* Store any kind of data at scale, such as for archiving, backup, restore and disaster recovery

### Blob Types
* Block
	* Store text and binary data up to 4.7TB. Made up of individually managed blocks of data
* Append
	* Block blobs that are optimized for append operations. Works well for logging where data is constantly appended
* Page
	* Store files up to 8TB. Any part of the file could be accessed at any time, for example a virtual hard drive

### Pricing Tiers
* Hot
	* Frequently accessed files. Lower access time and higher access costs
* Cool
	* Lower storage costs and higher access times. Data remains here for at least 30 days
* Archive
	* Lowest costs and highest access times


## Disk
### Managed Disk
* Azure Manages
	* You don't have to worry about backup and uptime
* Size and Performance
	* Microsoft and Azure guarantees size and performance as per your agreement with them
* Upgrade
	* Easy to upgrade your disk size and type

### Disk Types
* HDD
	* Spinning hard drive. Low cost and suitable for backups
* Standard SSD
	* Standard for production. Higher reliability, scalability, and lower latency over HDD
* Premium SSD
	* Super fast and high performance. Very low latency. Use for critical workloads
* Ultra Disk
	* For the most demanding, data-intensive workloads. Disks up to 64TB


## File
### On-Premises
* Issues
	* Constraints
		* You only have a limited amount of storage
	* Backups
		* Time and resources spent on maintaining backups
	* Security
		* It can be hard to keep all data secure at all times. Specialist assistance often needed
	* File Sharing
		* Can be difficult to share files across teams and organizations

### File Benefits
* Sharing
	* Share access to the Azure file storage across machines and provide access to your on-premises infrastructure
* Managed
	* You don't have to worry about hardware or operating system
* Resilient
	* Network and power outages won't affect your storage

### Scenarios
* Hybrid
	* Supplement or replace your existing on-premises file storage solution
* Lift and Shift
	* Move your existing file storages and related services to Azure


## Archive
### Overview
* Requirement
	* Policies, legislation, and recovery can be requirements for archiving data. these can be very large amounts of data
* Lowest Price
	* The archive tier is the lowest price of storage on Azure. A few dollars a month can get you terabytes of space
* Features
	* Durable, encrypted, and stable. Perfectly suited for data that is accessed infrequently
* Free Up Premium Storage
	* With cheap archive storage your can free up your more premium on-premises storage
* Secure
	* Fully secure to allow for any personal data such as financial records, medical data, and more
* Blob
	* Archive storage is blob storage, so the same tools will work for both


## Storage Redundancy
### Importance of Data Redundancy
##### Redundancy: Multiple, Replicated Copies of Data
If one copy fails/is inaccessible, data is still available.
Azure Storage always creates multiple copies of your data:
* Automatic
* Minimum of three copies
* Invisible to end user

### Multiple Redundancy Options
* Different location scopes
	* Single zone
	* Multiple zones
	* Multiple regions
* Higher availability = higher cost

### Redundancy Options at a Glance
* Single Region
	* Locally Redundant Storage (LRS)
	* Zone-Redundant Storage (ZRS)
* Multi-Region
	* Geo-Redundant Storage (GRS)
	* Geo-Zone-Redundant Storage (GZRS)

All options include:
* Three copies in primary region
* Three copies in secondary region (multi-region options)

### Locally Redundant Storage (LRS)
Three copies in a single location (datacenter/zone)
* Lowest-cost option
* Protect against single disk failure
* Does not protect against zone or regional outage

### Zone-Redundant Storage (ZRS)
Three copies across three availability zones
* One copy in each zone
* Protect against zone outage, but not regional outage

### Geo-Redundant Storage (GRS)
Three copies in two different regions
* Three copies in primary regional physical location (LRS)
* Three copies in secondary (paired) region physical location (LRS)
* Protect against primary region failure, but no primary region zone redundancy
* Can configure read access from secondary region for high availability

### Geo-Zone-Redundant Storage (GZRS)
Maximum redundancy!
* Copy across three availability zones in primary region (ZRS)
* Three copies in secondary region physical location/zone (LRS)
* Protect against primary region failure AND primary region zone failure
* Can also configure read access from secondary region for high availability

### Summing It Up
Azure Storage automatically replicates data for redundancy
* Three copies in single region
* Six copies across two paired regions
	* Three in each region
Redundancy options vary by availability and cost
* Single zone
* Multiple zones in a single region
* Across regions
	* Single/multi-zone in primary region


## Moving Data
### Concept: Moving Data into and Out of Azure Storage
Different solutions based on:
* Transfer frequency (occasional/continuous)
* Data size
* Network bandwidth

### AzCopy
Command-Line Utility
* Transfer blobs and Azure Files
* Useful for scripting data transfers

### Storage Explorer
Graphical User Interface (GUI) Interaction
* Download application
* User-friendly graphical interface
	* Drag-and-drop interaction
* Move all storage account formats

### Azure File Sync
Synchronize Azure Files with On-Premises File Servers
* Use cases:
	* Back up local file server
	* Synchronize files between multiple on-premises locations
	* Remote users access Azure Files
	* Transition to only Azure Files for file server


## Additional Migration Options
### Two More Migration Solutions
* Azure Data Box
* Azure Migrate

### Azure Data Box
Scenario: Transfer LOTS of data and/or limited bandwidth
* Lots = Too much to transfer over the internet
* Relative to available network bandwidth
Offline data transfer to/from Azure
Copy data to physical data storage device (Data Box)
* Encrypted
* Rugged
Ship Data Box to/from Azure
* To Azure: Data Box data transferred to storage account
* From Azure: Data Box delivered to on-premises location for on-site transfer

### Data Box Use Cases
* Initial bulk data migration
* Disaster recovery
	* Restore Azure backup to on-premises location
* Security Requirements
	* Sensitive data that cannot be sent over the internet

### Azure Migrate
Migrate non-Azure resources into Azure
* Servers
* Databases
* Applications

### Azure Migrate Scenario: Migrate Datacenter to Azure
* Discover dependent resources to migrate
* Migrate VMs
* Migrate databases to managed database services (e.g., Azure SQL)
* Migrate on-premises applications and dependencies
* Migrate bulk data with Data Box


## Premium Performance Options
Premium Performance Options for Low-Latency Requirements
* Stored on SSDs
	* Separate considerations from managed disk types
* Key considerations:
	* Available storage types for each performance option
	* Redundancy options
		* Trade more performance for less redundancy

### Storage Account Performance Options
* Standard
	* Standard general-purpose v2
		* The default -- supports all storage types
		* All redundancy options
* Premium
	* Premium block blobs
	* Premium page blobs
	* Premium file shares

### Premium Block Blobs
* Supported Storage Type
	* Blob Storage
	* Ideal for low-latency blob storage workloads
		* AI applications, IoT analytics
* Redundancy
	* LRS/ZRS only

### Premium Page Blobs
* Supported Storage Type
	* Page blobs
		* Unmanaged virtual disk
* Redundancy
	* LRS only (single zone)

### Premium File Shares
* Supported Storage Type
	* Azure Files
		* Ideal for high-performance enterprise (file server) applications
		* Supports both Server Message Block (SMB) and Network File System (NFS) file shares
			* Windows/Linux file shares
	* Redundancy
		* LRS/ZRS only

### Premium Storage Summary
Types of Storage Account
* Premium block blobs
	* Support Storage Services: Blob Storage
		* Redundancy Options: LRS/ZRS
* Premium page blobs
	* Support Storage Services: Page blobs only (IaaS disks)
		* Redundancy Options: LRS
* Premium file shares
	* Support Storage Services: Azure Files
		* Redundancy Options: LRS/ZRS


## Chapter 6 Summary
* Blob
	* General storage for anything you'd like
	* Block, append, and page varieties
	* Blob is inside a container, which is inside a storage account
	* Hot, cool, or archive price tiers
* Disk
	* A disk is generally attached to a VM; a managed storage service
	* Choose HDD, SSD, Premium SSD, or ultra disk
* File
	* Mitigating on-premises file storage solutions
	* Highly available and resilient storage
	* Easy to share
* Archive
	* A very cheap way to store massive amounts of data
	* Also a Blob Storage type

* Storage Redundancy
	* Multiple copies of Azure Storage data
	* Minimum three copies
	* Single/multiple copies
	* Single/multiple regions
* Moving Data
	* AzCopy: Command-line utility
	* Storage Explorer: GUI interface
	* Azure File Sync: Sync Azure Files with on-premises file server
* Additional Migration Options
	* Azure Data Box: Offline data transfer
	* Azure Migrate: Migrate on-premises resources
		* Servers, databases, applications
* Premium Performance Options
	* SSD-backed storage options
	* Limited redundancy options
	* Premium storage types


------


# Chapter 7 - Database (Supplemental)
## Cosmos DB
### Synchronization
* Easy with Cosmos
	* Traditional databases that weren't cloud enabled could be very difficult to set up across multiple regions. Azure takes care of all of it with Cosmos
* One Click to Add Regions
	* It's very easy to expand to more regions with Cosmos DB and have the data stay in sync
* Continued Synchronization
	* Cosmos DB stays on top of all reads and writes to your data and makes sure data is moved between regions to stay in sync

### Scalability
* Automated
	* Cosmos DB automatically scales to meet resource demand
* Infinite Resources
	* Any number of users of your application can be supported
* Lowest Price
	* Even though the scaling is automatic, you only pay for the resources you use

### Connectivity
* Developer
	* Choose from various software development kits (SDKs) and application programming interfaces (APIs)
* Languages
	* A language for most modern developers, including C#, Java, and Node.js
* Platforms
	* Choose from lots of data platforms to integrate with, including SQL, MongoDB, and Cassandra

### Warning!
Costs can run up quickly!


## Azure SQL
### Managed Service
Azure will take care of your hardware and infrastructural level needs (servers, storage, network, and everything else infrastructure related). Azure SQL just sits on top of this and provides the business logic and functions you need.
### Migration
* Frictionless Process
* Cost Saving
* Lower Total Cost of Ownership

### Built-in Machine Learning
* Optimization
	* Suggestions on how to optimize and improve performance of Azure SQL instances
* Warnings
	* You will get warnings of degrading instances, and if anything out of the ordinary is happening

### Cloud Benefits
* Scalability
	* Scale your Azure SQL instances and get high availability as well
* Space
	* Manage huge databases up to 100 Terabytes
* Security
	* Benefit from the built-in security features of the Azure cloud platform

### SQL Database vs. SQL Managed Instance
* Azure SQL Database
	* Most like traditional SQL Server
* Azure SQL Managed Instance
	* Aimed at migrating from on-premises


## Azure Database for MySQL
### Context
* SQL
	* Made by Microsoft
* MySQL
	* Made by the community

### MySQL Features
* Open Source
	* MySQL is an open source project where any member of the community can contribute
* Relational Database
	* Data in the database is connected through relations in the data itself
* Mature and Stable
	* Millions of applications and websites use MySQL. It's both a mature product and very stable

### Azure Advantages
* Platform-as-a-Service (PaaS)
	* The service infrastructure is managed by Microsoft
* Development Focus
	* Focus on developing your business strengths instead of managing servers and networks
* Choice of Language
	* Use the language and framework of your choice, such as PHP, and WordPress
* High Availability
	* Cloud glitter can provide high availability and scalability with ease. MySQL can handle an increasing number of users
* Azure Security Features
	* You get all the high standard Azure security features included
* Cloud Capabilities
	* All the cloudy PaaS features such as database patching, automatic backups and monitoring are included in the price

### MySQL Use Cases
* Web Applications
* E-Commerce
* Mobile Apps
* Digital Marketing
* Finance Management
* Gaming


## Azure Database for PostgreSQL
### PostgreSQL
* Open-Source Database
	* It's an open-source relational database, similar to MySQL
* Why The Name?
	* It came "post" the database Ingres, so the name became Postgres, which changed to PostgreSQL
* Free and Stable
	* It's free and very stable. Constantly improved since 1996. It's used in millions of installations

### Features
* Extensions
	* Use a large number of extensions, such as JSONB, geospatial functions, indexing, integration with tools and much more
* Horizontal Scaling
	* Use very high performant access to distributed data sets. In other words, use data faster across hundreds of servers
* Performance Recommendations
	* Get recommendations based on usage on how to make your database perform better. Get notifications of disruptive events
* Fully Managed
	* Azure gives you automatic database patching, automatic backups, and build-in monitoring

### PostgreSQL Use Cases
* Financial Applications
	* Ideal for online transactions and integrates with mathematical software
* Government
	* Governments use Postgres for geometric (GIS) data. One example is PostGIS, which is heavily used
* Manufacturing
	* Downtime is disastrous, and PostgreSQL provides automated failover and full redundancy


## Database Migration Services
### Database Migration
* Single Tool
	* One step migration for Microsoft SQL to Azure SQL
* Documentation
	* Comprehensive step-by-step guides and documentation for helping you migrate
* Guides for non-MS
	* Very detailed guides for migrating from non-Microsoft databases


## Chapter 7 Summary
### Azure Databases
* Cosmos DB
	* Globally distributed database. It's super fast and easy to manage. Scale to infinite performance and size
* Azure SQL
	* Fully managed and using stable Microsoft SQL Technology. Compatible with on-premises SQL severs
* Azure Database for MySQL
	* A very popular community driven open-source database that's used in millions of applications. Very robust and stable
* Azure Database for PostgreSQL
	* Also a very popular choice of relational database. Provides enterprise features like horizontal scaling. Azure offers a managed version
* Database Migration Services
	* Migration of almost any kind of database to Azure SQL or SQL Server. Guides, step-by-step instructions, comprehensive documentation


------


# Chapter 8 - Authentication and Authorization
## Identity Services
### Authentication
* Making sure you are you
* Confirming identity
* First test for access

### Authorization
* Comes after authentication
* Do you get access?
* Granular control

### Access Management
* Authentication vs. Authorization
	* You must know the difference to create effective access management
* Keep out the unwanted
	* Access management is critical to ensure only the right people and processes have access


## Azure Active Directory
### Active Directory
* Traditional Office Use
	* Active Directory was designed for traditional office use with computers and printers
* What is "Web"?
	* The web as a concept or service was not part of the design for Active Directory. Web services were not part of the original vision for Active Directory in 2000
* Authentication
	* Active Directory authentication uses services that aren't available on Azure

Active Directory is NOT Azure Active Directory.

### Azure Active Directory (AAD) Service
* Mandatory
	* You can't have an Azure account without an AAD service
* First User
	* Every Azure account needs a first user and this user is in the initial AAD instance

### Tenant
* Organization
	* A tenant represents the organization
* Dedicated AAD
	* A tenant is dedicated instance of AAD that an organization receives when signing up for Azure
* Separate
	* Each tenant is distinct and completely separate from other AAD tenants
* One User - One Tenant
	* Each user in Azure can only belong to a single tenant. Users can be guests of other tenants though

### Subscription
* Billing Entity
	* All resources within a subscription are billed together
* Cost Separation
	* You can have multiple subscriptions within a tenant to separate costs
* Payment
	* If a subscription isn't paid, all the resources and services associated with the subscription stop

### Hybrid Cloud Architecture
In a hybrid cloud architecture, you have some services on-premises and some services hosted on Azure. When you want to setup a hybrid cloud infrastructure, AAD can help manage your users both in the cloud on Azure and on your premises.

### Azure AD Now Part of Microsoft Entra
Microsoft Entra = New Product Family
* Includes all of Microsoft's identity and access capabilities
* Includes Azure AD, plus Permissions Management and Verified ID
* Exam perspective: Know that Azure AD is part of the broader Microsoft Entra product family

### Exam Tips
Manage users and permissions with Azure Active Directory.
* Active Directory(AD) is not the same as Azure Active Directory
* Different skillsets from AD to Azure AD
* Every Azure account will have an Azure AD service
* A tenant is a dedicated instance of Azure AD. It represents your organization in Azure
* A user belongs to a single tenant, but can be a guest in multiple
* A subscription is a billing entity. All resources belong to a single subscription
* Azure AD can help manage users in a hybrid cloud setup


## Zero Trust Concepts
### Classic Trusted vs. Untrusted Model
Trusted Perimeter
Trust boundary for secure access
* Example: Corporate network
* Restrict private access to secure networks

### Challenges with Trusted Perimeter Model
Must be on corporate network to access resources
* Remote work is a challenge
	* VPN is extension of trusted perimeter
* Mobile device access even more challenging
Rogue user/malware inside trusted perimeter network can cause havoc
* Broad scope of access

### Enter Zero Trust
What is Zero Trust?
* All users assumed untrustworthy unless proven otherwise
	* Trusted by identity
	* Regardless of location (trusted/untrusted network)
	* Least privilege access -- just enough permissions to perform job
	* Simplified, centralized managed
Zero Trust = Trusted Identities, Not Location

### Zero Trust in Action
Access Microsoft 365 email, documents, and resources for remote workforce
* Access from anywhere
* Authenticate with identity, not over VPN
Centrally control access with Conditional Access policies
Allow access only from approved managed devices
* Independent from network location


## Multi-Factor Authentication
### Approach
* Something you know
* Something you have
* Something you are

### Two Factor Authentication - Example
You are trying to log into a website that requires you to provide your valid email and password for authentication. Getting this correct is one factory of authentication. To make sure you credentials haven't been compromised, a code is sent to your phone, which you receive and enter into the website. The system uses something you know (your username/password) and something you have (your phone) to make sure you can get access into the website. MFA is enabled through Azure Active Directory.


## Conditional Access
### Conditional Access Concepts
Authentication Protections beyond Username/Password
* If/then policy to grant access
	* If (user) meets these conditions (signals), then grant/block access to defined applications
* Often paired with multi-factor authentication (MFA)
	* Centrally applied MFA enforcement
		* Does not rely on end user enabling MFA

### How It Works
Create Conditional Access Policy
* Assign signals (conditions)
	* Users/groups
	* Application to grant/deny access
	* Location (IP)
	* Approved devices
* Access decisions (grant/block access)
	* Grant access
	* Block access
	* Require MFA

### Conditional Access Scenarios
* Enforce MFA for all administrators/all users
* Block sign-ins using legacy authentication protocols
* Grant access only to specific locations
* Require organization-managed devices for application sign-in


## Passwordless Authentication
### Security vs. Convenience: The Never-Ending Conflict
Multi-Factor Authentication is More Secure, But Less Convenient
* More steps require to log in
	* Password and device/biometrics
	* Increased user frustration:
		* If everything is not working as expected
		* Overall, less convenient

### Passwordless Authentication: One Possible Solution
Objective: Increase Convenience While Staying Secure
* Password only = More convenient, but less secure
* Password + MFA = Higher security, but inconvenient
* Passwordless Authentication = High security and convenient
	* Remove password from system login
	* Replace with:
		* Something you have (phone/key fob)
		* Something you know/are (on device)
			* Fingerprint/face unlock/PIN

### Passwordless Authentication Methods
Microsoft Authentication App
* Microsoft's MFA mobile app
	* Configure in Azure AD
* Authenticate in app with biometrics/PIN
Windows Hello
* Face recognition in Windows
FIDO2 Security Key
* Hardware key

### Example Passwordless Login Scenario
* Log in to Microsoft 365, and enter your username.
* Instead of a password, you are prompted to check Microsoft Authenticator.
* Use  the biometric/PIN in the Authenticator app to confirm authentication
* Confirm numerical challenge in the Authenticator app


## External Guess Access
### Challenge: How Do You Collaborate With External Users?
Scenario: Working with outside consultant to streamline Azure or Azure AD configuration

Solutions?
Create separate organization account for external user
* Requires external user to juggle two accounts
Invite guest user to Azure tenant
* Guest user uses existing account as an external collaborator
* B2B collaboration

### Adding a Guest User
Invite a variety of account types (identity providers)
* Microsoft, Google, Facebook
* Other external identity providers
Assign permissions for guest account
* Principle of least privilege
* Different permissions between Azure AD and Azure subscription
Optional: Assign guest user to application
Optional: Apply cross- tenant Conditional Access policy
* Require MFA
* Require approved managed devices

### Scenario: Inviting an External Consultant
Configure identity provider (if non-Microsoft)
Invite external party
After guest user accepts invitation, assign permissions
* Optionally: Assign apps, apply Conditional Access policy


## Azure Active Directory Domain Services
### Limitations of Azure AD and Cloud Migrations
Legacy applications
* Unable to use modern authentication protocols (OAuth 2.0)
Require traditional Active Directory (AD DS) management/protocols
* Group Policy
* LDAP
* NTLM
* Kerberos

### Possible Solutions?
Continue using on-premises AD
* Sync to Azure AD with Azure AD Connect
Configure AD server on Azure VM
* Also known as self-managed AD DS
* You maintain/configure the operating system (OS)
Azure Active Directory Domain Services (Azure AD DS)
* Managed Active Directory Domain Services
* Provides classic AD features in a managed service
	* Group Policy, LDAP, Kerberos, domain join

### How Azure AD DS Works
Azure AD DS is a managed service
* No need for OS configuration/management
* Behind the scenes: two Windows domain controllers for high availability
Create unique namespace/domain name
* Example: aadds-companyname.com
* Standalone domain, not extension of on-premises AD domain
One-way sync from Azure AD to Azure AD DS
* Synchronize users, groups, and credentials
* Azure AD may also bidirectional sync with on-premises AD

### Azure AD DS Scenario
Lift and shift legacy enterprise application to Azure VMs
* Application does not support modern authentication
Requirement to integrate application with classic, cloud-hosted AD using managed services
Cloud-hosted legacy application authenticates with Azure AD DS


## Single Sign-On
### Concept
One pair of credentials for multiple services

### Azure SSO
Azure Active Directory Seamless Single Sign-On
* Enable SSO in AAD
* Seamlessly use all applications without logging in
* Single username and password


## Chapter 8 Summary
### Azure AD (AAD): A Central Component of Azure Authentication/Authorization
* AAD Is Fundamental!
	* You can't use Azure without AAD. AAD is not the same as Active Directory (AD)
* AAD Is First
	* The first service of every new account will be an AAD instance
* Tenant
	* Tenant = Organization
	* Single instance of AAD
	* A user account can be a member of a single tenant and can be a guest of up to 499 tenants
* Subscription
	* Billing entity that controls the cost of resources and services associated with it
* Hybrid Cloud
	* AAD can help you manage users in a hybrid cloud architecture between on-premises and in Azure

### Authentication/Authorization Topics
Zero Trust Concepts
* Everyone assumed untrustworthy unless proven otherwise
	* Regardless of location
* Trusted identities vs. trusted locations
* Necessary for remote work
Multi-Factor Authentication
* Extra layer of security using something you know, something you have, and something you are
Conditional Access
* If/then policy for granting access (i.e., conditions)
* Centralized management
* Examples:
	* Require MFA
	* Require managed device
Passwordless Authentication
* Bridge gap between security and convenience
* Remove system password
	* Replace with something you have/are
* Methods:
	* Microsoft Authenticator
	* Windows Hello
	* FIDO2 hardware security key

External Guest Access
* External collaboration
* Invite external user with existing account
* Works with many identity providers
	* Microsoft/Google/Facebook
Azure Active Directory Domain Services (Azure AD DS)
* Managed instance of Active Directory (AD DS)
* Integrates with classic AD features
	* Kerberos, LDAP, NTLM, Group Policy
* One-way sync with Azure AD
* Requires separate domain
Single Sign-On
* Use single username and password to log in to multiple applications using AAD


------


# Chapter 9 - Azure Solutions (Supplemental)
## Internet of Things
The Internet of Things is a system of interrelated computing devices, mechanical and digital machines, objects, animals or people that are provided with unique identifiers and the ability to transfer data over a network without requiring human-to-human or human-to-computer interaction.

### IoT Hub
It's a hub to collate data feeds from all your things. It's a backend, this system receives the data and manages it. It can receive data from billions of devices.

### IoT Hub - Features
* Managed and Secure
* Ease of Deployment
* Platform-as-a-Service
* Scaling and Authentication

### IoT Central
* Application Platform as a Service (aPaaS)
	* Simplify and speed up the implementation of your IoT solution
* No Coding Needed
	* You don't have to know how to write code to deploy your IoT project. Receive feeds from devices and focus on metrics and business value
* Pre-made Containers
	* Use any of the hundreds of connectors that are ready to use in IoT Central

### Solutions
* IoT Hub
	* PaaS solution that provides more control over the IoT data collection and processing
* IoT Central
	* aPaaS solution that provides pre-made IoT connections and dashboards to get set up quickly

### Internet of Things Azure Sphere
An all-in-one solution for IoT devices on Azure.
* Specific Hardware
	* You can only use hardware and chipsets certified by Microsoft for use on Azure
* Security
	* Specialized security service that manages maintenance, updates, and general control
* Operating System
	* Custom made for Azure Sphere devices. Connects to the Sphere Security Service


## Big Data
### Big Data - Moving Definition
* Data from Millions of Devices
* The definition of how big " Big Data" is changes as the industry can process more and more data

### Business Value
Big Data = Better service, better products, more profits

### Data Lake Analytics
* Large Amounts of Data
	* A data lake is a very large body of data
* Parallel Processing
	* Two or more processes or computers processing the same data at the same time. Data Lake Analytics includes parallel processing
* Ready to Go
	* Servers, processes and any other needed services are ready to go from the start. Jump straight into the data analytics

### HDInsights
* Similar to Azure Data Lake Analytics
* Open Source, which is free and community supported
* Includes Apache Hadoop, Spark, and Kafka

### Azure Databricks
* Based on Apache Spark, a distributed cluster-computing framework
* Run and process a dataset on many computers simultaneously
* Databricks provides all the computing power
* Integrates with other Azure Storage services

### Azure Synapse Analytics
* Azure's data warehouse offering
* Used to be Azure SQL Data Warehouse
* Used for reporting and data analysis
* Only limited by your scope
* Use Synapse SQL language to manipulate the data

### Outcomes
* Speed
	* Speed and efficiency of processing large amounts of data, provides real value
* Cost Reduction
	* Save large amounts of money on storage and processing, by using a Big Data solution in the cloud
* Better Decision Making
	* Immediate data processing and analysis in-memory means you can make better decisions, and make them faster
* New Products and Services
	* Understand what customers want and provide them with much better products and services


## Machine Learning
Artificial Intelligence is the capability of a machine to imitate intelligent human behavior. Through AI, machines can analyze images, comprehend speech, interact in natural ways, and make predictions using data.

### Machine Learning/AI
* Models
	* The definition of what your machine learning application is learning. A model is a set of rules of how to use the data provided. The model finds patterns based on the rules
* Knowledge Mining
	* Use Azure Search to finding existing insights in your data. File relationship, geography connections and more
* Built-in Apps
	* Azure has a number of built-in apps that you can use for machine learning and AI straight away. These include cognitive services and bot services

### Azure Bot Service
Azure PaaS offering that lets you build bots for Q&A services, virtual assistants, and more.
* Code or Visual
	* Create a bot using the visual editor or programming
* Language
	* Let users talk to your bot with natural language and speech integration
* Integration
	* Integrate the bot with other services, like Facebook Messenger, Teams, Twilio, and more
* Branding
	* Use your own branding and own the data the bot uses and produces

### Azure Cognitive Services
* Vision
	* You can use the vision service to recognize, identify, and caption your videos and images. Automatically
* Decision
	* Apps can make decisions based on content. Detect potential offensive language, detect IoT anomalies and leverage data analytics
* Speech
	* Automatic speech-to-text transcription. Speaker identification and verification

### Azure Machine Learning Studio
* Supports all Azure Machine Learning tools
* Pre-made modules for your project
* Use for real-world scenarios, such as Twitter sentiment analysis, photo grouping and movie recommendations

### Machine Learning Services
* End-to-End Service
	* The service to use AI and machine learning almost anywhere on Azure
* Tooling
	* The Machine Learning Service is a collection of tools to help you build AI application
* Automation
	* Azure automatically recognizes trends in your application and creates models for you


## Serverless
### Are there no servers?
Yes, there are servers. You just don't manage them, it's extreme PaaS.

### Azure Functions
* Golden Oldie
	* It's the first "serverless" service on Azure. The Azure service most will start with when exploring serverless architecture
* Single Task
	* It's called function as only a single task is performed every time. The function only runs once for each invocation
* Basic Compute Unit
	* It's a fundamental compute action and can be run millions of times per second if needed

### Logic Apps
* Connect Systems
	* Connect systems both inside and outside of the Azure platform. Integrate not only apps, but also data flows, services and entire systems
* Automation
	* A lot of ways to schedule, automate and orchestrate tasks and processes
* Quick Start
	* No coding required to get started straight away. You just need access to your apps to integrate

### Event Grid - What is an event?
An event is when an application wants the world (other connected applications) to know that something happened. It could be the placing of an order, for example. How do you get that event to the applications that need to know? This is where Event Grid comes in. Event Grid is a big network of connections to any service that wants it. You can connect most Azure products to it, and when they're connected, events are sent to Event Grid from which connected services can receive the events.

### Azure Event Grid
* Routing Service
	* Event Grid is a routing service for sending and receiving events between applications
* Serverless
	* No management of infrastructure components. Create a Azure Event Grid and start connecting services
* Ease of Use
	* Event Grid makes complex architecture simpler

### Exam Tips
Serverless approaches work extremely well with cloud services. ACG is all serverless.
* Yes, there are servers (they just aren't yours)
* Azure Functions are the most basic of compute tasks. Does one function then dies until next time it's called
* Logic Apps are a quick and simple way to integrate systems and applications inside and outside of Azure
* Event Grid is a routing service for passing events between applications that need to know about the events


## DevOps
DevOps is the work between development and production.

DevOps is at its core about people: how developers, engineers and system administrators organize themselves and work as a team to deliver better products faster.

### Azure DevOps
* Azure Boards
	* Keep track of work tasks, timelines, issues, planning and much more. Project managers love this part
* Azure Pipelines
	* Produce and test your software automatically and continuously
* Azure Repos
	* Store source code for your application securely in a managed way. Developers are big fans of this part
* Azure Test Plans
	* Design tests of applications to implement automatically. Quality assurance engineers love this
* Azure Artifacts
	* Share applications and code libraries with other teams inside and outside your organization
And it's FREE!

### Azure DevTest Labs
* Environment Management
	* Allow developers and engineers to create environments for test and development
* Cost Management
	* You won't incur unexpected costs and will even minimize waste of resources on your account
* Templates
	* Tailor your development and test environments and reuse them with templated deployments

### GitHub and GitHub Actions
* GitHub
	* Acquired in 2018 by Microsoft
	* code repository service for lots of big and small projects
	* A favorite among open-source communities
	* Microsoft themselves are one of the biggest users of GitHub
* GitHub Actions
	* Very similar to Azure Pipelines
	* Build code, test code, and publish code
	* Works with almost any platform, such as AWS, GCP, and many more


## Chapter 9 Summary
### Azure Solutions
* Internet of Things (IoT)
	* IoT is a network of millions of connected devices that function without human intervention. IoT Hub collates and manages data feeds as a PaaS product. IoT Central is a SaaS offering with templates and dashboards for a quick start
* Big Data
	* Processing and storage of very large data sets. Azure has Data Lake Analytics and HDInsight. This can lead to reduced cost, better decisions, and new products
* Machine Learning
	* Use rules and models to train your AI implementation. Azure Machine Learning Studio has pre-made models and tools to help you get started. Azure Machine Learning Service is a collection of tools
* Serverless
	* You are using someone else's servers. Azure Function is a single unit compute. Azure Logic Apps can connect data feeds and applications. Azure Event Grid is a network to route events between applications
* DevOps
	* Azure DevOps has 5 tools: Boards, Pipelines, Repos, Test Plans, and Artifacts. Use one or more in your workflow. Azure DevTest Labs lets you create full development and test environments easily and cost efficiently. GitHub and GitHub actions are tools that are similar to Azure DevOps


------


# Chapter 10 - Securiy
## Defense in Depth
### On-Premises Defense
* Physical Hardware
	* You are responsible for the security of the hardware, buildings, and staff
* Layers of Defense
	* You will have several layers of defense, as with a castle, such as swipe cards, security guards, firewalls, and more
* It's Up to You
	* You own the infrastructure, so you are responsible for adequate defense of hardware and data

### Azure
* Physical
	* Identity and Access
		* Perimeter
			* Network
				* Compute
					* Gateways and Firewalls
						* Data


## Securing Network Connectivity
### Firewall
* Rules
	* A firewall defines rules for what kind of traffic can and cannot access the device or service behind it
* Variations
	* Firewalls comes as hardware and software versions. They can suit any type and size of network
* Critical Part
	* Any network that take security serious will have a firewall

### Distributed Denial of Service Attacks - History
* U.S. Banks
	* In 2012, 6 U.S. banks were flooded with 60Gb of traffic every second
* CloudFlare
	* In 2014, CloudFlare was attacked with 400Gb of traffic per second
* GitHub
	* In 2018 GitHub experienced 1.35Tb of traffic per second. A new record for DDoS attacks

### DDoS Protection Service
* Many Internet-Connected Devices
	* A lot of computers and other connected devices target a single website to make it stop. GitHub had a 127M requests per second attack
* Protection
	* Detects the DDoS attack and deflects it. Various levels of protection depending on scenario
* No Downtime
	* There is no interruption to your service at all. Azure will mitigate the attack globally

### Network Security Groups (NSG)
* Resource Firewall
	* Personal resource firewall. Attach to virtual network, subnet or network interface
* Rules
	* A NSG determines who can access the resources attached to it, using rules for inbound and outbound traffic

### Network Security Group
For example, if you have a virtual machine that's on a virtual network, the network can be behind a firewall protecting everything on the network, and then the VM can have its own network security group to define specific rules for just that machine.

### Application Security Groups
* Protects Application Infrastructure
	* Focus the security on the application rather than the IP endpoint
* Natural Extension
	* Group VMs and virtual networks into logical application groups and apply an application security group


## Public and Private Endpoints
### Public Endpoints = Publicly Reachable PaaS Services
Default: Managed (PaaS) services reachable over the public internet
* Virtual network -> PaaS over public internet
* Also exposed to the public
* Problem with sensitive resources
What if we want to limit or remove public exposure?
Solution: Two available solutions: "Good" and "Better"
* "Good" = service endpoints
* "Better" = private endpoints

### Service Endpoints: "Good" Solution
Privately connect VNet subnet to Azure PaaS services
* Direct connection from subnet to Azure PaaS services
* Connects over Microsoft's private backbone (not over public internet)

Configure service to only allow traffic from service endpoint-enabled subnet
* Can also restrict access to specific public IP addresses

### Limitations of Service Endpoints
* Secure access to VNets only
	* No private on-premises access
	* Must allow on-premises access over public IP
* PaaS public endpoint still exists
	* Not truly private
* Service endpoints provide access to an entire service
	* For example, provides private access to all of Azure Storage, not just a single storage account

### Private Endpoint: "Better" Solutions
Managed network interface
* Private connection to specific instance of a service
* e.g., single storage account, SQL instance, etc

Available over connected networks
* Hybrid/on-premises networks
* Peered virtual networks

Can completely disable public access to a connected service
* Truly private
* Public endpoint disabled

### Scenario
VPN connection from home office to an Azure VNet named 'hub-vnet'

Must privately access sensitive Azure SQL database from home office
* Disable public internet exposure

Solution: A private endpoint
* Privately connects hub-vnet to Azure SQL database
* Private access from home office
* Can also disable public access for truly private connection


## Microsoft Defender for Cloud (formerly Azure Security Center)
### Overview
* It provides threat alerts
* It's ready for hybrid architectures
* Each VM has an agent installed that sends data
* Azure analyzes the data and alerts you if necessary

### Highlights
* Policy and compliance metrics
* A secure score to encourage great security hygiene
* Integrate with other cloud providers (requires Azure Arc)
* Alerts for resources that aren't secure

### Using Defender for Cloud
* Define Policies
	* Set up policies for Azure to monitor resources from. A policy is a set of rules used to evaluate a resource. Use predefined policies or create your own
* Protect Resources
	* Actively protect your resources through monitoring your policies and their outcomes
* Respond
	* Respond to any security alerts. Investigate all of them, and then go back to step 1 to define new policies to account for the alert


## Key Vault (Supplemental)
### Current Status
Attackers know where you keep your keys.

### Scenario
You have a database with some valuable business data in it. While you use the data successfully internally, you also want to share access to other trusted outside third parties. However you don't want to just give them the username and password to access the database. Instead, you place the password in Azure Key Vault and then provide access to individual applications. The application can identify itself, and then Azure Key Vault grants access to the database.

### Azure Key Vault
* Secure Hardware
	* The Key Vault hardware is secure too. Not even Microsoft can access the keys in it
* Application Isolating
	* An application can't pass on secrets, nor access another application's secrets
* Global Scaling
	* Scale globally like any other managed Azure service


## Azure Information Protection
* Classify data
	* Classify data according to how sensitive it's either using policies, or manually
* Track Activities
	* Track what's happening with shared data and revoke access if needed
* Share Data
	* Safely share data as you can control who edits, views, prints and forwards it
* Integration
	* Controls for document access is integrated with common applications and tools, such as Microsoft Office


## Microsoft Defender for Identity (formerly Azure Advanced Threat Protection) (Supplemental)
### Users Are Unreliable
You really can't trust users.

### The Constant Threat
If you have anything of value, it's almost guaranteed someone will probably want to get their hands on it. One way could be to target users specifically. Users are often the weakest link in an organization, and they can be tricked, coerced, and manipulated to provide details to assist attackers and to get them access to the corporation.

### Microsoft Defender for Identity
* Monitor Users
	* Analyze user activity and information. This includes any permissions and memberships of groups
* Baseline Behavior
	* Record what a user's normal behavior and routine is. Any activity outside this routine will be logged as suspicious
* Suggest Changes
	* Microsoft Defender for Identity will suggest changes to conform with security best practices in order to reduce risks

### Cyber-Attack Kill Chain
* Reconnaissance
	* If a user is searching for information about other users, device IP addresses and more, Microsoft Defender for Identity will raise alerts
* Brute Force
	* Any attempts to guess user credentials will be identified and flagged
* Increasing Privileges
	* Any attempt by a user to gain more privileges will be flagged. This could be through anther user's login


## Azure Sentinel (Supplemental)
### The What and the How
Sentinel is a security information and event management (SIEM) tool.
* Step 1: Data Collection
* Step 2: Aggregation and Normalization
* Step 3: Analysis and Threat Detection
* Step 4: Things Happen (Mostly Magic)
* Step 5: Take Action
Sentinel will do 90% of the heavy lifting before you even start investigating a potential security alert.

### Benefits and Features
* Behavioral Analytics
	* Sentinel uses artificial intelligence to learn if any detected behavior is unusual
* AWS Integration
	* Data from AWS services can be fed directly into Sentinel. This gives you one approach for threat detection across your multi-cloud infrastructure
* Cloud Scale
	* Sentinel can take advantage of the Azure cloud scale and deliver more accurate results fast


## Azure Dedicated Hosts (Supplemental)
### Dedicated Hosts
* Hardware Control
	* You get control of an entire physical server on Azure
* Yours and Yours Alone
	* Physical layer isolation means you won't get any "foreign" VMs on your dedicated host
* Maintenance
	* Reduce impact on your system by choosing when to install updates to your dedicated host

### Cloud Benefits
* Compliance
	* Take advantage of the stringent Azure compliance in combination with managing your own hardware
* Global Infrastructure
	* Availability zones, fault isolation, high availability, and scale sets come as standard. No optional extras here
* OS of Your Choice
	* Choose Windows, Linux, or SQL Server on a range of VM sizes. Even save money by using your own licenses


## Chapter 10 Summary
### Security Summary
* Defense in Depth
	* You need multiple layers of defense for your infrastructure. Azure has physical, identity, perimeter, network, compute, gateways and firewalls, and data as protection layers
* Securing Network Connectivity
	* A firewall controls the data coming and out of a network based on rules. Azure protects against DDoS attacks with no downtime to you. A network security group protects a subnet or virtual machine
* Public and Private Endpoints
	* Most Azure PaaS services are publicly reachable by default. Private endpoints enable private access to PaaS services. Can also disable public access for truly private services

* Microsoft Defender for Cloud (formerly Azure Security Center)
	* Monitor security hygiene for VMs. Define policies to protect your resources better and respond to incidents
* Azure Key Vault
	* A secure way to share access to applications and resources with third parties without ever revealing any credentials
* Azure Information Protection
	* Share files and data inside and outside of Azure and still maintain control over that data. You can control who views, edits, prints, and more

* Azure Sentinel
	* Collect, aggregate, analyze, and present security issues automatically for you to take action
* Azure Dedicated Hosts
	* Your own dedicated Azure hardware to install Windows, Linux, or SQL Server VMs on. Gives you control without losing cloud benefits like scaling, scale sets, fault isolation, and availability zones
* Microsoft Defender for Identity (formerly Advanced Threat Protection)
	* You secure and manage users of your organization. Monitor users' behavior, create a baseline of this behavior, and report on any anomalies from it


------


# Chapter 11 - Monitoring and Management
## Governance
Governance validates that your organization can achieve its goals through effective and efficient use of IT.

### What's a policy?
A policy is a set of rules, rules to make sure that standards and agreements within your corporation are followed and that resources are compliant with these policies.

### Role-Based Access Control (RBAC)
* Define User Access
	* You can define specific user access to individual resources
* Minimum Access
	* RBAC can enable minimum access necessary to resources. This ensures only users with valid access can manage resources
* Target Specific Use Cases
	* Be very explicit about uses and access. For example, allow an application access to certain resources or allow a user to manage resources in a resource group

### Role-Base Access Control - Role Assignment
* Security Principal
	* An object representing an entity such as a user or group, which can access the resource
* Role Definition
	* A collection of permissions such as read, write, and delete
* Scope
	* The resources the access applies to. Specify which role can access a resource or resource group

### Locks
* Assigning
	* Assign a lock to a subscription, resource group, or resource
* Types
	* A lock can be of two types. Delete, where you can't delete the locked object. Read-Only, where you can't make any changes to the object
* Locked Means Locked
	* A lock needs to be removed before the locked actions can be performed again

### Azure Blueprints
Blueprints are templates for creating Azure resources.
* Rules and regulations
	* Brand New Azure
		* Use Blueprints
			* Resource templates
			* Role Based Access Control (RBAC)
			* Policies
			* Samples for common regulations

### Cloud Adoption Framework
* Collection of Documents
	* Lots of resources to guide you through the cloud adoption process
* Guidance
	* Help to define strategies for adoption, planning the move, "being ready" for the cloud, adoption reasons, governance practices, and managing a living, breathing cloud architecture
* Governance
	* Key to the cloud adoption process is governance of the process. The Cloud Adoption Framework is a big step in that process

### Exam Tips
Governance keeps you complaint and out of trouble.
* Azure Policy ensures that policies applied to resources are compliant
* A policy is a set of rules to ensure complaint resources
* Role Based Access Control (RBAC) ensures user compliance through assigning a role to a user. A role is a combination of security principal, role definition and scope
* Locks make sure that subscriptions, resource groups or resources are either not modified or not deleted
* Blueprints are templates for creating standard Azure environments
* The Azure Advisor for Security Assistance is part of the Security Center


## Azure Monitor
"Telemetry is the collection of measurements or other data at remote or inaccessible points and their automatic transmission to receiving equipment for monitoring."

### Azure Monitor
* Constant Feed
	* Most Azure services feed telemetry data into Azure Monitor. Even on-premises services can send telemetry data to Azure Monitor
* Fully Managed
	* Azure Monitor is centralized and fully managed. You can analyze all the data from one place
* Query Language
	* Full access to an interactive query language to learn about the telemetry data
* Machine Learning
	* Predict and recognize problems faster with built-in machine learning

### Outcomes
* Maximize Performance
* Maximize Availability
* Identify Issues


## Monitoring Tools
### Monitor All the Things!
Azure includes multiple monitoring tools to gain full visibility into your Azure environment:
* Log Analytics
* Application Insights
* Azure Monitor Alerts

### Log Analytics
* Azure Monitor generates A LOT of logs and telemetry data
* Log Analytics stores and queries (or analyzes) that data to gain valuable insights
	* Examples:
		* VM disk size
		* VPN connection logs
		* Long term analysis
		* Combine metrics for complex queries

### Queries in Log Analytics
* Choose between pre-built and custom queries
* Queries in Kusto Query Language (KQL) format
  
### Application Insights
* Performance insights for web applications
* Answers questions:
	* "How are users using out app?"
	* "Where are our performance bottlenecks?"
	* "Why are we getting website errors?"

### Application Insights (Continued)
* Web apps only
* Available for App Service, Azure VMs, and non-Azure resources
	* VMs require installed agent
* Application Insights scenario
	* Find performance bottlenecks in web application
	* Discover how users are using the website

### Azure Monitor Alerts
When something breaks, alert someone to fix it!

Notifications in response to unexpected events
* Examples:
	* VM unresponsive
	* VM using excessive CPU
	* Application latency over 500 ms

### Alert Components
* Alert Rule
	* Monitored resource
	* Monitored telemetry
	* Conditions to trigger alert
	* Assigned severity
* Rule Example
	* Monitored resource: VM
	* Monitored telemetry: CPU utilization
	* Condition: > 90% CPU for 5 minutes
	* Severity: 2 - Warning
* Action group = action(s) taken when rule is triggered
	* Notification targets
		* Email/SMS to support personnel
		* Send to automation workflows (Logic Apps, Azure Functions, and more)
In all scenarios, when something is not working as expected, Azure Monitor alerts inform the right group to do something about it!


## Azure Service Health
### Maintenance
Azure needs to be updated and maintained just like any other computing infrastructure.

### Azure Service Health
* Dashboard
	* A personalized dashboard to highlight service issues affecting your resources
* Custom Alerts
	* Get notified of planned and non-planned outages. Alerts are simple to set up and customize
* Real-Time Tracking
	* Track any alerts and issues in real-time and get full reports once resolved
* Free Service
	* The Azure Service Health service is completely free


## Compliance (Supplemental)
### Industry Regulations
* General Data Protection Regulation
	* Main objective is to protect individuals and processing of their data. It gives control of personal data back to the individual, instead of the company owning it. Companies are required to implement a lot of tools for consumers to control their data
* ISO Standard
	* Many different ISO categories, such as compliance with quality and customer satisfaction. Most common is ISO 9001:2008. Also includes food safety and environmental management
* NIST
	* National Institute of Standards and Technology. Focuses purely on the tech industry. Developed primarily for US Federal agencies. Compliance with NIST means compliance with multiple Federal US regulations

### Azure Compliance Manager
Azure knows about compliance and resources, and can give you recommendations through the Compliance Manager.

* Recommendations
	* Get recommendations for ensuring compliance with GDPR, ISO, NIST, and others
* Tasks
	* Assign compliance tasks to team members and track progress
* Compliance Score
	* Chase a perfect score to be 100% compliant
* Secure Storage
	* Upload documents to prove compliance and store them securely
* Reports
	* Get reports of compliance data to provide to managers and auditors

### Azure Government Cloud
* Dedicated Regions
	* If you are a US government body or contract for one, you can get access. The Government Cloud consists of dedicated separate datacenters
* Exclusivity
	* You are a guaranteed only screened personnel from US federal, state and local government have access
* Compliance
	* Ensure compliance with required US government agencies, and level 5 Department of Defense approval
* Azure Benefits
	* You get standard Azure cloud benefits: high availability, scalability and managed resources

### China Region
* Located in China
	* Azure datacenter is physically located within China and has no connection outside of China, including other Azure regions
* Data is Kept in China
	* All customer data is kept inside Chinese borders. Certain global Azure services won't work fully
* Compliant
	* You are ensured compliance with Chinese regulations at all times

### Exam Tips
Compliance is not negotiable.
* GDPR, ISO, and NIST are regulations and standards to ensure compliance with applicable legislation
* Azure Compliance Manager provides recommendations, tasks to assign team members, a compliance score, secure document storage, and reports
* Azure Government Cloud provides dedicated datacenters to US Government bodies. Compliant with US federal, state, and local requirements
* Azure China region contains all data and datacenters within China. Complies with all applicable Chinese regulations


## Privacy (Supplemental)
### Azure Privacy
* Azure Information Protection
	* Classify, label, and protect data based on data sensitivity
* Azure Policy
	* Define and enforce rules to ensure privacy and external regulations
* Guides
	* Use guides on Azure to respond and comply with GDPR privacy requests
* Compliance Manager
	* Make sure you are following privacy guidelines


## Trust
### Trust Center & Service Trust Portal
* Trust Center
	* Learn about Microsoft's effort on security, privacy, GDPR, data location, compliance and more. A hub for more information about trust in each product and service
* Service Trust Portal
	* Review all the independent reports and audits performed on Microsoft's products and services. Azure complies with more standards than any other cloud provider


## Azure Arc

### The Challenge of Managing Complex Environments
Computing resources in multiple locations
* Microsoft Azure
* On-Premises
* Other Clouds (AWS, GCP)

Each computing source uses its own management tools
* More locations = more management overhead
* Cannot apply Azure governance policies to non-Azure resources

What if we could:
* Manage both Azure and non-Azure resources in the same interface?
* Apply Azure governance policies to non-Azure resources?
Solution: Azure Arc

### What's Azure Arc?
* Technical definition:
	* Centralized governance and management for on-premises and multi-cloud computing resources
* Simplified definition:
	* Manage non-Azure resources as if they were in Azure
	* Extend Azure cloud management and services to non-Azure locations

### How It Works
How Azure Arc works is that it effectively extends the Azure control management to our non-Azure locations. It works by installing an agent on these non-Azure computing resources to bring it into Azure's control plane. As a result, you Azure access and management is effectively extended from Azure to your non-Azure resources using Azure Arc as your bridge or connection between your non-Azure locations and Azure as well.

### Benefits of Azure Arc
* Manage Azure and non-Azure resources in the same place
* Manage non-Azure Kubernetes clusters
* Deploy Azure-managed database services to non-Azure locations
	* Example: Azure SQL Managed Instance
* Manage and protect non-Azure servers
	* Monitor non-Azure OSs alongside Azure VMs
	* Protect with Microsoft Defender for Cloud
	* Apply Azure Automation runbooks
* Apply Azure governance
	* RBAC
	* Azure Policies
	* Azure Blueprints
* Deploy Azure serverless services to non-Azure hardware
	* Azure App Service
	* Azure Functions
	* Azure Logic Apps
	* And more

### Scenario
You maintain servers in both Azure and an on-premises datacenter.
* You want to apply Azure management services (Azure Blueprints, Azure Policy) to these servers

Solution: Azure Arc


## Chapter 11 Summary
### Monitoring and Management
* Governance
	* Azure Policy, role-based access control (RBAC), resource locks, and Azure Blueprints
* Azure Monitor
	* Collect telemetry data from resources, which you can analyze. Maximize performance and availability and identify issues
* Monitoring Tools
	* Gain insights and receive alerts when something goes wrong with Log Analytics, Application Insights, and Azure Monitor alerts
* Azure Service Health
	* Notifies you about any planned and unplanned incidents on the Azure platform
* Compliance
	* Comply with GDPR and adhere to ISO and NIST standards. Use Compliance Manager to manage compliance. Azure Government and China regions
* Privacy
	* Core part of Azure and its products. Azure Information Protection, Azure Policy, and the GDPR guide are all privacy tools
* Trust
	* The Microsoft Trust Center is where you can find out what Microsoft does to keep your trust. The Service Trust Portal is where you can find audit reports and certificates awarded to Azure
* Azure Arc
	* Extend Azure's control plane to your non-Azure resources. Apply Azure governance to Azure and non-Azure resources


------


# Chapter 12 - Pricing
## Introduction
### Pricing Structure
* On-Premises
	* Utilization is well below 100%
	* No monthly costs
	* Large upfront cost
	* Pay for utilities
* Azure
	* You don't own the hardware
	* Pay for number of hours you use
	* Pay more for more resources
	* Service payment is tiered
	* Location can affect price


## Subscriptions
### Billing & Pricing
* Subscription
	* VM
	* Event Hub
	* Data Lake
	* HDInsight
All resources belong to a subscription

### Subscription
* Multiple Subscriptions
	* Any Azure account can have multiple subscriptions. Useful for organizing who pays for what
* Billing Admin
	* One or more users can be a "billing admin", which manages anything to do with billing and invoicing on Azure. Ensures separation of responsibility
* Billing Cycle
	* A billing cycle on Azure is either 30 or 60 days

### Offer Types
Offer types is the type of subscription. There are many different ones at any one time.
* Pay-as-you-go
* Support Plans
* Free trial
* Visual Studio Professional subscribers
* Visual Studio Test Professional subscribers
* MSDN Platforms subscribers
* Enterprise Dev/Test
* Etc

### Management Groups
* Group Subscriptions
	* Take action across subscriptions in bulk. Very useful in large organizations with many subscriptions
* Organize
	* Manage access, policies and compliance in bulk. E.g. have management group per country or department
* Billing Logic
	* You maintain the billing associated with the right budgets. Nest management groups to indicate hierarchy and relationship


## Cost Management
### Buying Azure Services
You can't use Azure without buying services and products. But there are many to buying services.

### Free Accounts
* Yes, it's free
* Benefits
	* Many free services, as Microsoft wants you to get a taste of what Azure has to offer. Virtual Machines, databases, storage, and more
* Always Free
	* Some services are always free for everyone. Some totally free, some partially free up to a threshold

### Free Accounts
Your first Azure project could be free.
* Need a valid credit card
* Only one free account per Microsoft Account

### Azure Cost Management
* Azure Portal
	* Access the Azure Cost Management tool from within the Azure Portal. get a detailed view of current and projected costs. Azure Cost Management is free and included with all Azure subscriptions
* Reports & Recommendations
	* Get detailed spending reports and recommendations on how to save on costs and analyze them
* Optimization
	* Optimize your current resources to save money and monitor any AWS charges too

### Spot VM
* Save money by using unused computing capacity
* The VM can be evicted at any time by Microsoft if they need the compute power back
* Use for interruptible non-critical workloads
* Use with Azure scale sets
* Set a max price for the Spot VM


## Pricing Factor
### Influences on Pricing
* Resource Size
	* Different sizes of resources will have different pricing. A more powerful virtual machine will cost more
* Resource Type
	* There is a very big difference in the amount of hardware resources needed for various types of resources, as well as complexity
* Location
	* Different Azure locations have different prices for services. Exchange rates, labor costs and more have an influence on the price
* Bandwidth
	* The bandwidth your services are using incurs a cost as well

### Zones & Bandwidth
Azure has three billing zones in the world. Each of these zones include many Azure regions. Any data transfer between Azure services located in the same zone is free. Any data transfer between two different billing zones is charged. This is also called ingress, data in, and egress, data out, data. Ingress data is always free, but egress data (data going out) has a cost with it when it's transmitted between two different billing zones.

### Pricing Calculator
* Choose from all available Azure services
* Select resource properties, such as for a Virtual Machine
* Monthly cost estimate
* Export estimate for further analysis and use

### Total Cost of Ownership Calculator
* Get an estimate of the total savings you could get for moving your on-premises resources to Azure
* Estimate total savings over a period of time by using Azure
* Comprehensive reports to share with stakeholders


## Best Practices
### Spending Limits
* Default Limit
	* Some Azure accounts with monthly credits to use will have default spending limits. When the credits are used, the limit kicks in
* No Increase
	* When the credits are gone, either remove the limit entirely or leave it in effect
* No Spending Limit
	* Pay-as-you-go accounts have no spending limit functionality

### Quotas
* Property Limit
	* A quota is a limit on a certain property of an Azure service. For example, a maximum of 100 namespaces for Event Hub
* Ensure Service Level
	* The quotas are necessary to ensure Azure can maintain their high service level
* Quota Change
	* If you need to increase the quota for a particular service, you can ask Microsoft to increase them

### Tags
* Tags are non-functional labels that attach to a resource or resource group
* Use as many tags as you want

### Tags - Continued
* Identify Roles
	* Protect sensitive data by defining which roles can access a resource
* Related Resources
	* To make bulk processing and updating easier, define which resources are related
* Filter
	* Filter resources per project, customer or for reporting purposes
* Unambiguous
	* Create a list for tags used that includes: description, tag name, and potential values

### Pay-as-you-go
Pay-as-you-go = Expensive

### Reserved Instances
Reserved instances can save you a lot of money. Not all Azure services can be reserved.

### Reserved Capacity
* 1-or 3-Year commitment
	* Azure SQL
		* Save up to 80%
	* Synapse Analytics
		* Save up to 65%
	* Cosmos DB
		* Save up to 65%
	* Redis Cache
		* Save up to 55%
Change regions, scale up or down, apply it to multiple subscriptions, and cancel at any time.

### Azure Hybrid Benefits
Azure will let you use existing licenses instead of forcing you to purchase new ones with every new VM or server.

### Advisor
The Advisor portal gives you best practices advice in general through recommendations.


## Chapter 12 Summary
### Pricing
* Subscriptions
	* Every resource belongs to a subscription. An Azure account can have multiple subscriptions. Billing admins control costs. Management groups help you keep track of many subscriptions in an account
* Cost Management
	* Use free accounts and Azure Cost Management to keep costs as low as possible and optimize resources
* Pricing Factors
	* Resource size, resource type, location of the service and bandwidth used all affect the price of a service. Azure Pricing Calculator and Total Cost of Ownership Calculator can help predict costs
* Best Practices
	* Use spending limits, quotas for services, tags to order resources and reserved instances to manage costs and get the best price


------


