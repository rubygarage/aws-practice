# AWS VPC

## VPC - Virtual Private Cloud

Amazon Virtual Private Cloud (Amazon VPC) lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways. You can use both IPv4 and IPv6 in your VPC for secure and easy access to resources and applications.

- Within a Region, you’re able to create VPCs (Virtual Private Cloud)
- Each VPC contains subnets (networks)
- Each subnet must be mapped to an AZ
- It can have a public subnets (public IP)
- It can have a private subnets (private IP)

<br>

## VPC Subnet
---
## Subnet - logical subdivision of the network
<img src="https://i.imgur.com/kB8ZVux.png" width="400" height="320" />

<br>

#### Public subnets can access.
#### Private subnets cannot access to Internet initialy, but can throuh NAT interface.

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
<br>

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
<br>

## Internet Gateway
---
### Internet Gateway - hardware network interface (Network card) that allows data to flow from one network interface to another. In our case: from public subnets to global Internet
<img src="https://i.imgur.com/xv1ehEk.png" width="400" height="320" />

<br>
<br>

## Route Table
---
### Route table contains a set of rules, called routes, that are used to determine where network traffic from your subnet or gateway is directed.

### Route Table Concepts

Your VPC has an implicit router, and you use route tables to control where network traffic is directed. Each subnet in your VPC must be associated with a route table, which controls the routing for the subnet (subnet route table). You can explicitly associate a subnet with a particular route table. Otherwise, the subnet is implicitly associated with the main route table. A subnet can only be associated with one route table at a time, but you can associate multiple subnets with the same subnet route table.

**Main route table** — the route table that automatically comes with your VPC. It controls the routing for all subnets that are not explicitly associated with any other route table.

**Custom route table** — a route table that you create for your VPC.

**Edge association** - a route table that you use to route inbound VPC traffic to an appliance. You associate a route table with the internet gateway or virtual private gateway, and specify the network interface of your appliance as the target for VPC traffic.

**Route table association** — the association between a route table and a subnet, internet gateway, or virtual private gateway.

**Subnet route table** — a route table that's associated with a subnet.

**Gateway route table** — a route table that's associated with an internet gateway or virtual private gateway.

**Local gateway route table** — a route table that's associated with an Outposts local gateway. For information about local gateways, see Local Gateways in the AWS Outposts User Guide.

**Destination** — the destination CIDR where you want traffic to go. For example, an external corporate network with a 172.16.0.0/12 CIDR.

**Target** — the target through which to send the destination traffic; for example, an internet gateway.

**Local route** — a default route for communication within the VPC.

<br>

## NAT Gateway
---
### NAT (Network Address Translation) - technology that allows your instances with private IP communicate with Global Internet by remmaping private address to public using NAT table

<img src="https://qph.fs.quoracdn.net/main-qimg-56413cede35ff6c11ff66cfbf2d5c780"/>


