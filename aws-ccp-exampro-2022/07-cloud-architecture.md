# Cloud Architecture

Solutions Architect - role in a technical organization that architects a technical solution using multiple systems via researching, documentation, and experimentation

Cloud Architect - a solutions architect solely focused on technical solutions using cloud services

Availability = ability to ensure service remains highly available (HA)
Scalability = ability to grow rapidly or unimpeded
Elasticity = ability to shrink and grow to meet the demand
Fault Tolerance = ability to prevent a failure
Disaster Recovery = ability to recover from a failure, ie: highly durable (DR)

Solutions Architects need to always be asking:

1. How secure is this solution?
2. How much is this solution going to cost?

High Availability = ability for service to remain available by eliminating single points of failure and possibly ensuring a certain level of performance

Enabled on AWS by running workload across multiple AZs to ensure app remains available even if 1-2 AZs become unavailable

- can use Elastic Load Balancer to route traffic

High Scalability = ability to increase capacity based on increasing demand of traffic, memory and computing power

- vertical scaling / scaling up = upgrade to bigger server
- horizontal scaling / scaling out = add more servers of the same size

High Elasticity = ability to automatically increase/decrease capacity based on current traffic/memory/computing power demand

Vertical Scaling is generally hard for traditional architecture - usually elasticity refers to horizontal scaling

Horizontal scaling

- scaling out = add more servers of the same size
- scaling in = removing underutilized servers of the same size

Autoscaling Groups (ASGs) can use preconfigured rules to determine scaling

Fault Tolerance = remove single points of failure to reduce the likelihood of overall system failure

Fail-overs = a plan to shift traffic to redundant system if primary system fails

- IE: maintain a copy (secondary) of yoru DB where all ongoing changes are synced. Secondary system is not in-use until a fail-over occurs and it becomes the primary DB

- can accomplish with RDS multi-AZ, running another DB as a standby in another AZ

High Durability = ability to recover from a disaster and to prevent the loss of data

Disaster Recover (DR) = solutions that help recover from a disaster

- do you have a backup?
- how fast can you restore that backup?
- does your backup still work?
- how do you ensure current live data is not corrupt?

- CloudEndure Disaster Recovery continuously replicates machines into a low-cost staging area in target AWS account and region, enabling fast/reliable recovery in case of IT data center failures

Business Continuity Plan (BCP) = document outlining how a business will continue operating during an unplanned disruption in services

- Recovery Point Objective (RPO) = maximum acceptable amount of data loss after an unplanned data-loss incident, expressed as an amount of time (How much data are you willing to lose?)
- Recovery Time Objective (RTO) = maximum amount of downtime your business can tolerate without incurring significant financial loss (How much time are you willing to go down?)

Disaster Recovery Options
Backup & Restore = back your data and restore it to new infrastructure (RPO/RTO = Hours)

- lower priority use cases
- restore data after event
- deploy resources after event
- cost = $

Pilot Light = Data is replicated to another region with the minimal service running (RPO/RTO = 10 minutes)

- small RTO/RPO
- core services
- start & scale resources after event
- cost = $$

Warm Standby = Scaled down copy of your infrastructure is running, ready to scale up (RPO/RTO = minutes)

- business critical services
- scale resources after event
- cost = $$$

Multi-Site Active/Active = Scaled up copy of infrastructure is running in another region (RPO/RTO = realtime)

- zero downtime
- near zero loss
- mission critical services
- cost = $$$$ (same as regular infrastructure)
