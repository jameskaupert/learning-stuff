# Containers

## VMs vs Containers

VMs = sit on top of hypervisor and host OS. Will always have wasted space

- do not make best use of space
- apps not isolated which could cause
  - config conflicts
  - security problems
  - resource hogging

Containers = sit on top of Docker Daemon and host OS. No wasted space because containers expand/shrink to space they need

- allow you to run multiple apps, virtually isolated from one another
- launch new containers and configure OS dependencies per container

## Microservices

Monolithic Architecture = one app which is responsible for everything. Functionality is tightly coupled

Microservices Architecture = multiple apps, each of which are responsible for one thing. Functionality is isolated and stateless

## Kubernetes

Kubernetes (k8) = open-source container orchestration system for automating deployment, scaling and management of containers

- originally created by Google, now maintained by the Cloud Native Computing Foundation (CNCF)

commonly called K8 for the remaining lettings in `ubernete` (despite missing the 's')

Advantage over Docker is ability to run containers distributed across multiple VMs

A unique component of Kubernetes are Pods

Pods = group of one or more containers with shared storage, network resources, and other shared settings

Kubernetes is ideal for micro-service architectures with 10s-100s of services to manage

## Docker

- set of Platform as a Service (PaaS) that use OS-level virtualization to deliver software in packages called containers
- earliest popularized open-source container platform

Dockerfile = configuration file on how to provision a container

Open Container Initiative (OCI) = open governance structure for creating open industry standards around container formats and runtime. Established by Docker, now maintained by the Linux Foundation

Docker has been losing favor due to newer paid open-source model. Alternatives like Podman are growing.

## Podman / Buildah and Skopeo

Podman = container engine that is OCI-compliant and is a drop-in replacement for Docker

- daemon-less (Docker uses containerd daemon)
- allows you to create pods like K8 (Docker does not have pods)
- Podman only replaces one part of Docker. Podman is to be used alongside Buildah and Skopeo

Buildah = tool used to build OCI images

Skopeo = tool for moving container images between different types of container storages

## Container Services

Primary Services:

- Elastic Container Service (ECS)
  - no cold starts
  - self-managed EC2
- AWS Fargate
  - more robust than Lambda
  - scale to zero cost
  - AWS-managed EC2
- Elastic Kubernetes Service (EKS)
  - open-source
  - no vendor lock-in
- AWS Lambda
  - only think about code
  - short running tasks
  - can deploy custom containers

Provisioning and Deployment

- Elastic Beanstalk (EB)
  - ECS on training wheels
  - PaaS
- App Runner
  - PaaS, specifically for containers
- AWS Copilot CLI
  - build, release, and operate production-ready containerized applications on AWS App Runner, ECS, and Fargate

Supporting Services

- Elastic Container Registry (ECR)
  - Repos for Docker images
- X-Ray
  - Analyze and debug between microservices
- Step Functions
  - stitch together Lambdas and ECS tasks
