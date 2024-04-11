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