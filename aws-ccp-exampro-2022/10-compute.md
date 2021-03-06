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

### Higher Performance Computing Services

The Nitro System = combination of dedicated hardware/lightweight hypervisor that enable faster innovation/enhanced security. All new EC2 instance types use Nitro system

- Nitro cards = specialized cards for VPC, EBS, and Instance storage and controller card
- Nitro security chips = integrated into motherboard, protecting hardware resources
- Nitro hypervisor = lightweight hypervisor memory and CPU allocation - bare metal-like performance

Baremetal Instance = instances you can launch with no hypervisor so you can run workloads directly on the hardware for maximum performance and control. M5 and R5 instances are bare metal

Bottlerocket = Linux-based open-source OS that is purpose-built by AWS for running containers on VMs or bare metal hosts

High Performance Computing (HPC) = a cluster of hundreds of thousands of servers with fast connections between them, each with the purpose of boosting computing capacity

- ie: a supercomputer to perform computation problems too large to run on standard computers or that would take too long

AWS ParallelCluster = AWS-supported open-source cluster management tool. Makes it easy to deploy and manage HPC clusters on AWS

## Edge & Hybrid Computing Services

Edge Computing - push computing workloads outside of your networks to run close to the destination location, ie: pushing computing to run on phones, IoT devices, or external servers not within your cloud network

Hybrid Computing - run workloads both on your on-premise datacenter and AWS Virtual Private Cloud (VPC)

AWS Outposts = physical rack of servers you can put in your datacenter. Lets you use AWS services right within your datacenter

AWS Wavelength = build and launch apps in telecom datacenter. Applications have ultra-low latency since they are pushed over a 5G network to be as close as possible to the end user

VMWare Cloud on AWS = manage on-premise virtual machines using VMWare as EC2 instances. Datacenter must be using VMWare for virtualization

AWS Local Zones = edge datacenters located outside of an AWS region so you can use AWS closer to the end destination

## Cost & Capacity Management Computing Services

Cost management = how do we save money?
Capacity management = how do we meet the demand of traffic and usages through adding or upgrading servers?

EC2 Spot Instances, Reserved Instances and Savings Plans = ways to save on computing by paying up front in full or partially, by committing to yearly contracts, or by being flexible about availability and interruption to computing service

AWS Batch = plans, schedules, and executes batch computing workloads, and can utilize Spot Instances to save money

AWS Compute Optimizer = suggests how to reduce costs and improve performance by leveraging machine learning to review and analyze your previous usage history

EC2 Autoscaling Groups (ASGs) = automatically add/remove EC2s to meet current demand of traffic. Saves money and meets capacity by only running the amount of servers you need

Elastic Load Balancer (ELB) = distribute traffic to multiple instances, or re-route traffic from unhealthy instances to healthy ones. Can route to EC2s in different AZs

AWS Elastic Beanstalk (EB) = easily deploy web apps without setting up and managing underlying AWS services (like Heroku)
