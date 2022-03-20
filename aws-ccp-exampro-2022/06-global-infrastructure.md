# Global Infrastructure

## Basics

- globally distributed hardware and datacenters that are physically networked together to act as one large resource for the end customer

- made up of
  - 26 launched regions
  - 84 availability zones
  - 108 direct connect locations
  - 310+ points of presence
  - 14 local zones
  - 20 wavelength zones

See [https://aws.amazon.com/about-aws/global-infrastructure/](https://aws.amazon.com/about-aws/global-infrastructure/) for up to date stats

## Regions

- geographically distinct locations consisting of one or more AZs
- physically isolated from and independent of every other region in terms of location, power, water supply
- generally 3 AZs per region, but sometimes 2
- usually new services first become available in US-EAST
- not all services available in all regions
- all billing info in US-EAST-1
- costs of services vary by region

## Factors for Choosing a Region

1. regulatory compliance
1. cost of AWS services within the region
1. availability of services within the region
1. distance and latency to end users

## Availability Zones

- a physical location made up of one or more datacenters
- secured buildings with many computers
- generally 3x AZs per region
- datacenters within a region will be isolated from one another (different buildings), but close enough to provide low latency (<10ms) - within 60mi/100km of each other
- common practice to run workloads in at least 3 AZs for High Availability if one or two datacenters fail

Subnets are associated with AZs

- you never choose an AZ when launching resources - subnets are chosen instead

## Fault Tolerance

Fault Domain = section of a network vulnerable to damage if a critical device or system fails. The purpose of a fault domain is that if a failure occurs, it will not cascade outside that domain, limiting possible damage

Fault level = collection of fault domains. Can be scoped however (servers in a rack, rack in a datacenter, room in a datacenter, entire datacenter...)

AWS abstracts fault level so you don't have to worry about it (an AWS region would be a Fault Level, an AWS AZ would be a Fault Domain). Azure does not (you get to pick)

Each region is designed to be completed isolated from other regions for fault tolerance and stability

Each AZ is isolated, but connected to other AZs within the region with low-latency links
Each AZ is an independent failure zone.

- They are physically separated within a metro region and located in lower risk flood plains
- They have discrete, uninterruptible power supplies and onsite backup generation
- They are designed to be supplied by different substations to reduce the risk of a power grid event impacting more than a single AZ
- AZs connected redundantly to various tier-1 transit providers.

Applications using multi-AZ are better isolated/protected from issues such as power outages, lightning strikes, tornados, earthquakes, and more

## AWS Global Network

- represents interconnections between AWS Global Infrastructure - often called the "backbone of AWS"
- private expressway capable of moving things very fast between datacenters

Edge Locations can act as "on and off ramps" to the AWS Global Network

- ie: on ramps like AWS Global Accelerator & AWS S3 Transfer Accelerator
- ie: offramps like CloudFront, to provide Edge storage and compute near the end user

VPC Endpoints ensure resources stay within AWS Network and do not traverse the public internet

## Points of Presence (PoP)

- Intermediate location between an AWS region and the end user. This could be a datacenter or collection of hardware
  - owned by AWS or a trusted partner, utilized by AWS services for content delivery or expediated upload
  - ie: edge locations / regional edge caches
  - live at the edge or intersection of two networks

Edge Locations - datacenters holding cached copies of the most popular files so delivery time due to distance to end users is reduced

Regional Edge Locations - hold much larger caches of less-popular files to reduce full round trip and reduce cost of transfer fees

Tier 1 Network = network that can reach every other network on the internet without purchasing IP transit or paying for peering

- AWS AZs are redundantly connected to multiple Tier-1 transit providers

Some AWS Services using PoPs for content delivery or expediated upload:

- Amazon CloudFront - Content Delivery Network (CDN) service that
  - you point website to CloudFront so it routes requests to nearest Edge Location cache
  - allows you to choose an _origin_ such as web-server or storage that is the source of the cache
  - caches the contents of what the origin would return to various Edge locations around the world
- Amazon S3 Transfer Acceleration - allows you to generate special URL that can be used by end users to upload files to nearby Edge Location. From there, it can move much faster within the AWS Network to reach S3
- AWS Global Accelerator - finds optimal path from end user to your web servers. Deployed within Edge Locations so you send user traffic to an Edge Location instead of directly to web app

## AWS Direct Connect

AWS Direct Connect = private/dedicated connection between your datacenter/office/co-location and AWS. Near zero latency

- two very fast network connection options

1. Lower Bandwidth: 50MBps-500MBps
2. Higher Bandwidth: 1GBps or 10GBps

- helps reduce network costs and increase bandwidth throughput
- provides more consistent network experience than typical internet connection (reliability/security)

Direct Connect Locations = trusted partner datacenters to help establish dedicated high speed / low-latency connection from your on-prem to AWS

## AWS Local Zones

- datacenters located very close to high population areas, designed to provide single-digit millisecond latency for that area
  - first local zone is in Los Angeles, CA, and is a logical extension to the US-West region
  - only specific services are available
  - must opt-in to Local Zones via support ticket
  - used for highly demanding applications sensitive to latency
    - media/entertainment
    - electronic design automation
    - ad-tech
    - machine learning

## Wavelength Zones

- allow for edge-computing on 5G telecom networks
- Ultra-low latency
- AWS partners with telecom companies to utilize their 5G networks
- you create a subnet tied to the Wavelength Zone and can launch VMs (on EC2s) to the edge of the targeted network

## Data Residency

Data Residency = the physical or geographic location where an organization or cloud resources reside

Compliance Boundaries = regulatory compliance (legal requirements) by government or organization describing where data/cloud resources are **allowed** to reside

Data Sovereignty = jurisdictional control or legal authority that can be asserted over data because its physical location is within jurisdictional boundaries

When you need to meet compliance boundaries that strictly define the data residency of data/cloud resources in AWS, you can use:

1. AWS Outposts = physical rack of servers you can put in your data center. Data resides wherever the outpost resides
2. AWS Config = Policy-as-Code service that allows creation of rules to continuously check AWS resource configuration. If deviations are identified, you can be alerted or in some cases have auto-remediation
3. IAM Policies can be written to explicitly deny access to specific AWS regions. A **Service Control Policy** (SCP) sets up permissions that are applied organization wide

## AWS For Government

- Public Sector = public goods and governmental services such as
  - military
  - law enforcement
  - infrastructure
  - public transit
  - public education
  - health care
  - the government itself

AWS can be utilized by public sector or organizations developing on behalf of the public sector

AWS achieves this by meeting regulatory compliance programs and specific governance and security controls

AWS has special regions for US regulation called GovCloud

### GovCloud

FedRAMP = Federal Risk and Authorization Management Program - US government-wide program providing standardized approach to security assessment, authorization, and continuous monitoring for cloud products and services

GovCloud = an isolated region to run FedRAMP workloads

- allow customers to host sensitive Controlled Unclassified info and other types of regulated workloads
- only operated by employees who are US citizens, on US soil
- only accessible to US entities and root account holders passing a screening process

Customers on GovCloud can architect secure cloud solutions complying with:

- FedRAMP
- DOJ Criminal Justice Information Systems (CJIS)
- US International Traffic in Arms Regulations (ITAR)
- Export Administration Regulations (EAR)
- Department of Defense (DoD) Cloud Computing Security Requirements guide

### AWS In China

AWS China is completed isolated (intentionally) from AWS Global to meet regulatory compliance for Mainland China. AWS China is on its own domain at amazonaws.cn

In order to operate in AWS China Regions, you need a Chinese Business License (ICP license)

Not all services are available in China (ie: Route53)

Running in Mainland China (instead of Singapore) means you do not need to traverse The Great Firewall

## Sustainability

- Amazon co-founded the Climate Pledge to achieve Net-Zero Carbon Emissions by 2040 across all of Amazon's businesses, including AWS
  https://sustainability.aboutamazon.com

3 Main Parts to AWS Cloud Sustainability Goals:

1. Renewable Energy - working to 100% renewable energy powering global infrastructure by 2025

- purchases and retires environment attributes to cover non-renewable energy uses (Renewable Energy Credits - RECs & Guarantees of Origin - GOs)

2. Cloud Efficiency - 3.6 times more efficient than median of other U.S. enterprise data centers surveyed
3. Water Stewardship - use direct evaporative technology to cool datacenters, recycled non-potable water for cooling, on-site water treatment to remove scale-forming minerals for more water reuse cycles, and water metrics to monitor efficiency

## AWS Ground Station

AWS Ground Station = fully managed service providing satellite communications, and associated data processing and operations scaling without having to build and manage dedicated ground station infrastructure

- download satellite data to an associated EC2 and dump to S3

## AWS Outposts

AWS Outposts = fully managed service offering AWS infrastructure, services, APIs, and tools to any datacenter/co-location space/on-premise facility for hybrid cloud

- rack of servers running AWS infrastructure at your physical location
