# What is VPC?

Amazon Virtual Private Cloud (Amazon VPC) lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways. You can use both IPv4 and IPv6 in your VPC for secure and easy access to resources and applications.

Create VPC:

> *left menu* Your VPCs => Create VPC => *Enter name* (MyVPC) => *IPv4 CIDR block* 10.0.0.0/16 => *Tenancy* Default => Create

- Within a Region, you’re able to create VPCs (Virtual Private Cloud)
- Each VPC contains subnets (networks)
- Each subnet must be mapped to an AZ
- It can have a public subnets (public IP)
- It can have a private subnets (private IP)
