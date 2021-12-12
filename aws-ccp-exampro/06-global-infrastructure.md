# Global Infrastructure

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
- datacenters within a region will be isolated from one another (different buildings), but close enough to provide low latency (<10ms)
- common practice to run workloads in at least 3 AZs for High Availability if one or two datacenters fail
