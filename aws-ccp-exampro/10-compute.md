# Compute

## EC2

Elastic Compute Cloud (EC2) allows you to launch Virtual Machines (VMs)

Virtual Machine (VM) = emulation of a physical computer using software

- server virtualization allows you to easily create, copy, resize, or migrate your server
- multiple VMs run on the same physical server so you can share the cost with other customers
- kind of like if your server / computer was an executable file on your computer
- a launched VM is called an **instance**

EC2 is a highly configurable server where you can choose an Amazon Machine Image (AMI) with options for things like:

- amount of CPUs
- amount of Memory (RAM)
- amount of Network Bandwidth
- OS
- attachment of multiple virtual hard drives for storage (Elastic Block Store (EBS))

Amazon Machine Image (AMI) = predefined configuration for a VM

EC2 is considered the backbone of AWS, because most AWS services are using EC2 as their underlying servers

## Amazon LightSail

Amazon Lightsail = managed virtual server service. Friendly version of EC2 for if you don't have much AWS knowledge

## Containers

Containers = virtualizing an OS to run multiple workloads on a single OS instance. Often used in microservices architecture where application is comprised of multiple smaller applications that talk to each other

### Elastic Container Service (ECS)

- container orchestration service that supports Docker containers
- launches cluster of server(s) on EC2 instances with Docker installed

### Elastic Container Registry (ECR)

- repository for container images
- versioned storage for container images

### Fargate

- serverless orchestration container service
- same as ECS, but you pay on-demand per running container instead of keeping an EC2 server running even if you have no containers running
- AWS manages the underlying server so you don't have to scale or upgrade it

### Elastic Kubernetes Service (EKS)

- fully managed Kubernetes service
- Kubernetes (K8) is open-source orchestration software used generally for managing microservices

## Serverless / AWS Lambda

When underlying servers are managed by AWS. You don't worry about or configure servers

- AWS Lambda is a serverless functions service
  - run code without provisioning/managing servers
  - upload small pieces of code, choose memory and how long function is allowed to run before timing out
  - charged based on the runtime of the serverless function rounded to the nearest 100ms
