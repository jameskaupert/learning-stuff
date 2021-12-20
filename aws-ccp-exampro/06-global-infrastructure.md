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
