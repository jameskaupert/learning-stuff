# Cloud Concepts

## Cloud Computing

> The practice of using a network of remote servers hosted on the internet to store, manage, and process data, rather than a local or personal computer

### On-Premise

- you own the servers
- you hire personnel
- you pay/rent land to house it
- you take all the risk

### Cloud Providers

- someone else owns the servers
- someone else hires personnel
- someone else pays/rents land to house it
- you are responsible for configuring services/code, but someone else handles the rest

## Evolution of Cloud Hosting

- Dedicated Server

  - one physical machine for a single business, running a single app/site
  - very expensive
  - high maintenance
  - high security

- Virtual Private Server (VPS)

  - one physical machine for a single business, virtualized into sub-machines to run multiple apps/sites
  - better utilization and isolation of resources

- Shared Hosting

  - one physical machine, shared by many businesses, relying on tenants under-utilizing their resources
  - very cheap
  - limited functionality
  - poor isolation

- Cloud Hosting
  - multiple physical machines that act as one system
  - system abstracted into multiple cloud services
  - flexible
  - scalable
  - secure
  - cost-effective
  - high configurability

## What is AWS

- collection of cloud services capable of being used together under a single API to implement many types of workloads
- launched in 2006, and is the leading cloud service provider (CSP) in the world
- SQS was the first service in 2004
- S3 was added in 2006
- EC2 added in 2006
- by 2010, all of amazon.com was using AWS
- certifications added in 2013

## What is a Cloud Service Provider (CSP)?

- company which
  - provides multiple cloud services
  - that can be chained together to create cloud architectures
  - that are accessible via a single unified API
  - that use metered billing based on usage
  - that have rich monitoring built in
  - that have an Infrastructure as a Service (IaaS) offering
  - that offer automation via Infrastructure as Code (IaC)

Companies offering multiple cloud services but do not meet most/all of the above, they are Cloud Platforms instead

## Landscape of CSPs

Tier 1 (early to market, wide offering, strong synergies between services)

- AWS
- Microsoft Azure
- Google Cloud Platform (GCP)
- Alibaba Cloud (China-specific)

Tier 2 (backed by well-known tech giants, slow to innovate and specialize instead)

- IBM Cloud
- Oracle Cloud
- Rackspace (OpenStack)

Tier 3 (VPS adding additional IaaS offering - simple, cost-effective)

- Vultr
- Digital Ocean
- Linode

## Common Cloud Services

4 most common types of cloud services for IaaS:

1. Compute
2. Networking
3. Storage
4. Databases

## Evolution of Computing

### Dedicated

- physical server, wholly utilized by a single customer (single tenant)
- have to guess on capacity
- overpay for an underutilized server
- can't vertically scale without a manual migration
- replacing a server is difficult
- limited by host operating system
- multiple apps can result in conflicts in resource sharing
- more secure, if you do a good job of it

### VMs

- you run multiple VMs on one machine
- hypervisor is the software layer that lets you run VMs
- physical server shared by multiple customers
- pay for a fraction of the server
- overpaying if underutilized
- limited by guest operating system
- resource sharing conflicts if multiple apps running on a single VM
- easy to migrate (export/import images)
- easy to scale vertically or horizontally

### Containers

- virtual machine running multiple containers
- Docker Daemon software layer lets you run multiple containers
- maximize utilization of available capacity (more cost-effective)
- containers share underlying OS, so more efficient than multiple VMs
- multiple apps run side by side, not restricted to same OS, and do not cause conflicts during resource sharing

### Functions

- managed VMs running managed containers
- known as serverless compute
- upload a piece of code, choose amount of memory and duration
- only responsible for code and data, nothing else
- very cost-effective, only pay for time code is running, VMs only run when there is code to be executed
- code start is a side-effect of the setup time

## Types of Cloud Computing

Software as a Service (SaaS) [For Customers] - product run and managed by service provider. Service just works and remains available (Gmail, Office365, etc...)

Platform as a Service (PaaS) [For Developers] - focus on the deployment and management of your apps; don't need to provision, configure, or understand the hardware or OS (Heroku, Elastic Beanstalk, Google App Engine)

Infrastructure as a Service (IaaS) [For Administrators] - basic building blocks of cloud IT. Provides access to raw networking, computers, and storage, etc...Don't worry about personnel, data centers, hardware

## Cloud Computing Deployment Models

Public Cloud - everything is built on the CSP (aka Cloud-Native or Cloud-First)

Private cloud - everything is built on company's data centers (aka on-premise)

Hybrid cloud - combo of public/private

Cross-Cloud - using multiple CSPs (aka multi-cloud)

## Deployment Model Use Cases

Cloud - companies starting out today, small enough to make the leap

- startups
- SaaS offerings
- new projects/companies

Hybrid - companies starting with their own datacenter or can't fully move to cloud due to migration effort or compliance

- banks
- FinTech / Investment Management
- large profession service providers
- legacy on-premise

On-Premise - companies that cannot run on cloud due to strict regulations or sheer organization size

- public sector / government
- sensitive data
- large enterprise with heavy regulation
