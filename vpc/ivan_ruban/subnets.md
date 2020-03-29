# Subnets

Subnet is a range of IP addresses in your VPC.
A VPC spans all of the Availability Zones in the Region. You can add one or more subnets in each Availability Zone. Each subnet must reside entirely within one Availability Zone and cannot span zones. Availability Zones are distinct locations that are engineered to be isolated from failures on other Availability Zones. By launching instances in separate Availability Zones , you can protect your applications from the failure of a single location.

### Public Subnets usually contains:
* Load Balancers
* Static Websites
* Files
* Public Authentication Layers

### Private Subnets usually contains:
* Web application servers
* Databases
* Public and private subnets can communicate if they’re in the same VPC!

### Private Subnets can have IP in that ranges:
```ruby
10.0.0.0 - 10.255.255.255
172.16.0.0 - 172.31.255.255
192.168.0.0 - 192.168.255.255
```

## Create subnets:

> Subnets => Create subnet => *Enter name* Public SN => *VPC* MyVPC => *IPv4 CIDR block* 10.0.1.0/24 => Create
> Subnets => Create subnet => *Enter name* Private SN => *VPC* MyVPC => *IPv4 CIDR block* 10.0.2.0/24 => Create

## Architecture public/private subnets:

![](pics/architecture-of-vpc.png)

## Also AWS reserved **5** ip addresses for each CIDR block. For example **10.0.0.0/8**:
```yml
10.0.0.0 - Network address.
```
```yml
10.0.0.1 - Reserved by AWS for the VPC router.
```
```yml
10.0.0.2 - Reserved by AWS. The IP address of the DNS server is the base of the VPC network range plus two. For VPCs with multiple CIDR blocks, the IP address of the DNS server is located in the primary CIDR. We also reserve the base of each subnet range plus two for all CIDR blocks in the VPC. For more information, see Amazon DNS Server.
```
```yml
10.0.0.3 - Reserved by AWS for future use.
```
```yml
10.0.0.255 - Network broadcast address. We do not support broadcast in a VPC, therefore we reserve this address.
```
