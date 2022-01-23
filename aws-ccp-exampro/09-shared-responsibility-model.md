# Shared Responsibility Model

Shared Responsibility Model = cloud security framework that defines the security obligations of the customer against the Cloud Servicer Provider's obligations

Customers are responsible for security "in" the cloud (Data & Configuration)

AWS / CSPs are responsible for security "of" the cloud (Hardware, Operation of Managed Services, Global Infrastructure)

## Types of Cloud Computing Responsibility

The higher the level of customer control, the higher the level of customer responsibility

The customer is always responsible for the data and the configuration of access controls that resides in AWS

The customer is responsible for the configuration of cloud services and granting access to users via permissions

CSP is generally responsible for the underlying infrastructure (bare metal cases aside)

On-Premise

- you (the custoemr) are responsible for everything

Infrastructure as a Service

- you are responsible for Applications, Data, Runtime, Middleware, & OS
- CSP is responsible for Virtualization, Servers, Storage & Networking

Platform as a Service

- you are responsible for Applications & Data
- CSP is responsible for Runtime, Middleware, OS, Virtualization, Servers, Storage & Networking

Software as a Service

- CSP is responsible for everything

### Shared Responsibility Model - Compute

Infrastructure as a Service

1. Bare metal (EC2 Bare Metal Instance)

- Customer:
  - Host OS configuration
  - Hypervisor
- AWS:
  - physical machine

2. Virtual Machine (EC2)

- Customer:
  - guest OS configuration
  - container runtime
- AWS:
  - Hypervisor
  - physical machine

3. Containers (ECS)

- Customer:
  - configuration of containers
  - deployment of containers
  - storage of containers
- AWS
  - OS
  - Hypervisor
  - Container Runtime

Platform as a Service (Elastic Beanstalk, sort of)

- Customer:
  - uploading code
  - some configuration of environment
  - deployment strategies
  - configuration of associated services
- AWS:
  - Servers
  - OS
  - Networking
  - Storage
  - Security

Software as a Service (Amazon WorkDocs)

- Customer:
  - Contents of documents
  - Management of files
  - Configuration of sharing access controls
- AWS:
  - Servers
  - OS
  - Networking
  - Storage
  - Security

Function as a Service (Lambda)

- Customer:
  - Upload your code
- AWS:
  - Deployment
  - Container Runtime
  - Networking
  - Storage
  - Security
  - Physical Machine
  - basically everything...

### Shared Responsibility Model - Architecture

Less Responsibility (serverless/functions)

- things like Amplify Serverless Framework & Lambda
- no more servers, just worry about the data and code

Medium Responsibility (microservices/containers)

- things like Fargate/ECS/EKS
- mix and match languages, get better utilization of resources

High Responsibility (traditional / VMs)

- things like Elastic Beanstalk and EC2
- Global workforce is most familiar with this type of architecture
