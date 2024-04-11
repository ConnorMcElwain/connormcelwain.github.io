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