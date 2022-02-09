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
