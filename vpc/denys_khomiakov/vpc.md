# VPC - Virtual Private Cloud

## Basic info

VPC - is the service aimed to give an ability to create and configure AWS resources inside your own network.
You can have several VPCs within one AWS region, but you can't have VPC that contains several instances from different regions.

This is a simple schema with public and private subnets, route tables and access control lists (ACL):

![](pics/architecture-of-vpc.png)

- Internet Gateways allows communication between instances in your VPC and the internet.
- Route table consists from different routes (rules), that define where traffic will be directed.
- ACL serves like first step of the VPC's defense (the second is a security group), you can create allow-rules or deny-rules and also block different IP addresses.
- Security group is virtual firewall that controls inbound and outbound traffic.
- Subnet ("SN" on the schema) is a range of IP addresses in your VPC. It can be public - accessible from internet, or and private - can be reached through public instance.

When you create EC2 instance, by default it has all necessary components to work with VPC (Internet Gateway, Route Table, ACL and public subnet).

## Bastion Hosts

If you want to SSH to your instance in the private subnet, you will have to do it through instance in your public subnet.
In such case your public instance would be Bastion Host. Then you can make your public instance as secure as possible, and also your private instance will be even more secured.

How to make it from scratch:

> Sevices => VPC

1. Create VPC:

> *left menu* Your VPCs => Create VPC => *Enter name* (MyVPC) => *IPv4 CIDR block* 10.0.0.0/16 => *Tenancy* Default => Create

2. Create subnets:

> Subnets => Create subnet => *Enter name* Public SN => *VPC* MyVPC => *IPv4 CIDR block* 10.0.1.0/24 => Create
> Subnets => Create subnet => *Enter name* Private SN => *VPC* MyVPC => *IPv4 CIDR block* 10.0.2.0/24 => Create

3. Make "Public SN" public:

> Subnets => *Choose Public SN* => *right click* Modify auto-assign IP settings => *Auto-assign IPv4* check => Save

4. Create Internet Gateway:

> Internet Gateways => Create internet gateway => *Enter name* MyIGW => Create
5. Attach Internet Gateway:


> Internet Gateways => *Choose MyIGW* => *right click* Attach to VPC => MyVPC => Attach

6. Create Route Table:

> Route Tables => Create route table => *Enter name* MyRT => MyVPC => Create

7. Config routes:

> Route Tables => *Choose MyRT* => *Routes tab* Edit routes => Add route => *Destination* 0.0.0.0/0 => *Target* Internet Gateway => MyIGW => Save routes

8. Config subnet associations:

> Route Tables => *Choose MyRT* => *Subnet Associations* Edit subnet associations => Public SN => Save

To be continued...
