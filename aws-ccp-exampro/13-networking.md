# Networking

## Cloud-Native Networking Services

VPC = logically isolated section of the AWS Cloud where you can launch AWS resources

Internet Gateway = enable access to the internet

Route Tables = determine where network traffic from subnets are directed

Region = geographical region of your network

AZ = data centers where your AWS resources reside

Subnets = logical partition of an IP network into multiple smaller network segments

Security Groups = act as a firewall at the instance level

NACLs = act as firewalls at the subnet level

## Enterprise/Hybrid Networking

AWS Virtual Private Network (VPN) = secure connection between on-premise, remote offices, and mobile employees

DirectConnect = dedicated gigabit connection from on-premise data-center to AWS (very fast, not necessarily private)

PrivateLinks (VPC Interface Endpoints) = keeps traffic within AWS network and not traverse internet to keep traffic secure

## VPCs and Subnets

Virtual Private Cloud (VPC) = logically isolated section of the AWS network where you launch your AWS resources

- you choose a range of IPs using CIDR range

Subnets = logical partitions of IP network into multiple smaller segments. Break up IP range for VPC into smaller networks

Subnets needs to have a smaller CIDR range to represent their portion

- 10.0.0.0/16 = 65,536 IP addresses
- 10.0.0.0/24 = 256 IP addresses

Public subnet = one that can reach the internet
Private subnet = one that cannot reach the internet
