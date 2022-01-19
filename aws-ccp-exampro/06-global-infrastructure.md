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
