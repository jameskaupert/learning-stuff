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
