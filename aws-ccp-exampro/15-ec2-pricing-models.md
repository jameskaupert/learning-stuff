# EC2 Pricing Models

1. On-Demand - least commitment

- low cost and flexible
- pay per hour/second
- short-term, spiky, unpredictable workloads that cannot be interrupted
- for first-time apps

2. Spot (up to 90%) - biggest savings

- request spare computing capacity
- flexible start/end times
- can handle interruptions (server randomly stopping/starting)
- for non-critical background jobs

3. Reserved (up to 75% off) - best long-term

- steady state or predictable usage
- commit to EC2 over 1 or 3 year term
- can resell unused reserved instances

4. Dedicated - most expensive

- dedicated servers
- can be on-demand or reserved or spot
- when you need guarantee of isolated hardware due to enterprise requirements

5. Savings Plans

## On Demand

- pay as you go (PAYG) model, where you consume compute, then you pay
- when you launch an EC2 it is by default using on-demand pricing
- no up-front payment, no long-term commitment
- charged by the second (minimum 60s) or the hour

## Reserved Instances (RI)

- designed for steady-state, predictable usage, or require reserved capacity
- reduced pricing based on term x class offering x RI attributes x payment option

Term = the longer the term the greater the savings

- commit to 1 or 3 year contract
- does not auto-renew
- when it expires, instance will use on-demand pricing with no interruption to service

Class = the less flexible the greater the savings

- Standard = up to 75% reduced pricing compared to on-demand. Can modify the RI attributes
- Convertible = up to 54% reduced pricing compared to on-demand. Can exchange RI based on RI attributes if greater or equal in value
- Scheduled = no longer offered by AWS

Payment Options = the greater the upfront the greater the savings

- all upfront = full payment made at the start of the term
- partial upfront = a portion of the cost must be paid upfront, remaining hours in term billed at discounted hourly rate
- no upfront = billed at discounted hourly rate for every hour within the term, whether or not the RI is being used

RIs can be shared between multiple accounts within an AWS organization

Unused RIs can be sold in the RI Marketplace

### Reserved Instance Attributes

- limited based on Class Offering and can affect final price of RI

4 RI Attributes

1. Instance Type = instance family and size
2. Region = region in which RI is purchased
3. Tenancy = Whether instance runs on shared (default) or single-tenant (dedicated) hardware
4. Platform = OS

### Regional and Zonal RI

When you purchase an RI, you determine the scope of the RI. Scope does not affect price

#### Regional RI

- purchase for a region
- does _not_ reserve capacity
- discount applies to instance usage in any AZ in that region
- discount applies to instance usage within the instance family regardless of size. Only supported on Amazon Linux / Unix RIs with default tenancy
- can queue purchases for regional RIs

#### Zonal RI

- purchase for an AZ
- reserves capacity for the specified AZ
- discount applies to instance in the selected AZ (no flexibility on AZ)
- no instance size flexibility
- discount applies to instance usage for specified type and size only
- cannot queue purchases for zonal RIs

### RI Limits

- limits to number of RIs you can purchase per month
- 20 regional RIs per region, 20 zonal RIs per AZ

## Capacity Reservations

- EC2s backed by specific hardware, so there are a finite number of servers available in an AZ per instance type or family
- Capacity Reservation is an EC2 service allowing request to reserve EC2 instance type for specific region & AZ
- Reserved capacity is charged at selected instance type's on-demand rate whether an instance is running or not
- can use regional RIs with capacity reservations to save some money

## RI Marketplace

- allows you to sell unused standard RIs to recoup money for RIs you cannot or do not intend to use
- must have been active at least 30 days, and once AWS has been paid the upfront if applicable
- need a US bank account
- must be at least a month remaining
- seller can set only the upfront price. Usage price and config remain the same as when the RI was initially purchased
- term length is rounded down to nearest month
- can sell up to $20,000 in RIs per year
- cannot sell GovCloud RIs on the marketplace

## Spot Instances

AWS has unused compute capacity. They want to maximize the utility of idle servers.

- Spot instances provide 90% discounts compared to on-demand pricing, but can be terminated if capacity required by other on-demand customers
- designed for apps with flexible start/end times that can handle interruptions and are only feasible at very low compute costs
- AWS Batch service is an easy / convenient way to use Spot Pricing
- terminated instances (stopped by AWS) do not receive partial usage hour charge from AWS
- terminated instances (stopped by you) are charged for any hour they ran

## Dedicated Instances

- designed to meet regulatory requirements
- when you have strict server-bound licensing that won't support multi-tenancy or cloud deployments

Multi-tenancy is like everyone living an apartment - virtual isolation separates customers using the same hardware for multiple workloads

Single-tenancy is like everyone living in their own house - physical isolation is what separates customers

## Savings Plans

- offer similar discounts as RIs, but with simplied purchasing process
- 3 types
  - Compute
  - EC2 instance
  - SageMaker
- two terms (1 or 3 year)
- payment options
  - all upfront
  - partial upfront
  - no upfront
- you choose the hourly commitment

Compute savings plans provide most flexibility (up to 66% cost reduction). Apply to EC2 instances, Fargate, and Lambda regardless of instance family, size, AZ, region, OS, or tenancy

EC2 instance savings plans provide lowest prices (up to 72% cost reduction). Commitment to individual instance families within a region. Works regardless of AZ, size, OS, tenancy, and allows changing between instances in the same family

SageMaker savings plans help reduce costs (up to 64%), regardless of instance family, size, component, or region
