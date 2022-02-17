# Well-Architected Framework

Well-Architected Framework = whitepaper created by AWS to help customers build using best-practices defined by AWS

https://aws.amazon.com/architecture/well-architected

Divided into sections called pillars which address different aspects or "lenses" that can be applied to a cloud workload

- general definitions
- general design principles
- the review process

If the foundation (based on the pillars) is not solid, structural problems will arise

Pillars

- Operational Excellence
- Security
- Reliability
- Performance Efficiency
- Cost Optimization
- Sustainability

Each pillar has its own whitepaper too

### Well-Architected Framework - General Definitions

Operational Excellence = run and monitor systems
Security Pillar = protect data and systems, mitigate risk
Reliability Pillar = Mitigate and recover from disruptions
Performance Efficiency Pillar = use computing resources efficiently
Cost Optimization Pillar = get the lowest price

Sometimes pillars will need to be traded off against one another based on the business context to achieve the most business value

Component = code, configuration, and AWS resources against a requirement
Workload = set of components that work together to deliver business value
Milestones = key changes of your architecture through product lifecycle
Architecture = how components work together in a workload
Technology Portfolio = collection of workloads required for the business to operate

### On Architecture

The AWS Well-Architected framework is designed around a different kind of team structure

Enterprises generally have centralized teams with specific roles, where AWS has distributed teams with flexible roles

Distributed teams come with new risks. AWS mitigates these with practices, mechanisms, and leadership principles

On-Premise Enterprise

- centralized team consisting of
  - technical architect (infrastructure)
  - solution architect (software)
  - data architect
  - networking architect
  - security architect
    (managed by either TOGAF or Zachman Framework)

AWS

- distributed teams consisting of
  - practices
    - team experts who look for ways to raise the bar
  - mechanism
    - automated checks for standards
  - Amazon Leadership Principle
    (supported by a virtual community of SMEs, Principal Engineers, thru lunchtime talks that get recycled into onboarding material)

## Amazon Leadership Principles

Set of principles used by Amazon for:

- decision-making
- problem solving
- simple brainstorming
- hiring

1. Customer Obsession
2. Ownership
3. Invent and Simplify
4. Are right, a lot
5. Learn and be curious
6. Hire and develop the best
7. Insist on the highest standards / raise the bar
8. Think Big
9. Bias for Action
10. Frugality
11. Earn Trust
12. Dive Deep
13. Have backbone - disagree and commit
14. Deliver results
15. Strive to be Earth's best employer
16. Success and scale bring broad responsibility

See more at https://www.amazon.jobs.en/principles

## General Design Principles

1. Stop guessing your capacity needs - cloud computing uses as little or as much as you need based on demand
2. Test systems at production scale - clone production environment to testing, then tear it down when not in use to save money
3. Automate to make architectural experimentation easier - use CloudFormation, etc...
4. Allow for evolutionary architectures - CI/CD, rapid/nightly releases, lambdas deprecating run-times forcing you to evolve
5. Drive architectures using data - CloudWatch/CloudTrail automatically turned on for collecting data - use this!
6. Improve through game days - simulate traffic on production or purposefully kill EC2 instances to test recovery

## Pillar Anatomy

All pillars follow the same structure

- Design Principles - list of principles to consider during implementation
- Definition - overview of the best practice categories
- Best Practices - detailed information about each best practice with AWS services
- Resources - additional docs, whitepapers, and videos to implement the pillar

### Operational Excellence

Design Principles

- perform operations as code
  - Apply same engineering discipline you would to application code to your cloud infrastructure
  - operations as code helps limit human error and enables consistent responses to events
- make frequent, small, reversible changes
  - design workloads to allow components to be updated regularly
  - rollbacks, incremental changes, blue/green, CI/CD
- refine operations procedures frequently
  - look for continuous opportunities to improve your operations
  - use game days to simulate traffic or event failure on your production workloads
- anticipate failure
  - perform post-mortems on system failures to better improve
  - write test code
  - kill production servers to test recovery
- learn from all operational failures
  - share lessons learned in a knowledge base for operational events and failures across your entire organization

### Security

Design Principles

- implement a strong identity foundation
  - Implement Principle of Least Privilege
  - use centralized identity
  - avoid long-lived credentials
- Enable traceability
  - monitor, alert, and audit actions and changes to your environment in real-time
  - integrate log and metric collection
  - automate investigation and remediation
- apply security at all layers
  - take defense in depth approach with multiple security controls for everything
- automate security best practices
- protect data in transit and at rest
- keep people away from data
- prepare for security events
  - incident management systems and investigation policy and processes
  - tools to detect, investigate, and recover

### Reliability

Design Principles

- Automatically recover from failure
  - monitor KPIs and trigger automation when threshold breached
- Test recovery procedures
  - test how workload fails, and validate your recovery procedures
  - use automation to simulate different failures or recreate failure scenarios from the past
- Scale horizontally to increase aggregate system availability
  - replace one large resource with multiple small resources to reduce the impact of a single failure on the overall workload
  - distribute requests across multiple, smaller resources to ensure they don't share a common point of failure
- Stop guessing capacity
  - you don't need to guess because you can request the right size of resources, on-demand
- manage change in automation
  - make changes via IaC, allowing for a formal process to track and review infrastructure

### Performance Efficiency

Design Principles

- Democratize Advanced Technologies
  - focus on product development rather than procurement, provisioning, management
  - take advantage of advanced technology specialized and optimized for your use-case with on-demand cloud services
- go global in minutes
  - deploying workload in multiple regions around the world allows you to provide lower latency and better experience for your customers at minimal cost
- use serverless architectures
  - removes the need to run and maintain physical servers for traditional compute activities
  - removes operational burden of managing physical servers and can lower transactional costs because managed services operate at cloud scale
- experiment more often
  - with virtual and automatable resources, you can quickly do comparative testing with different types of instances, storage, or configurations
- consider mechanical sympathy
  - consider consumption patterns of cloud services and use tech approach best aligned with your workload goals. IE: consider data access patterns when selecting database or storage approaches
