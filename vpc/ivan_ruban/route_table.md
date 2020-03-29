# Route Table

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

## Create Route Table:

> Route Tables => Create route table => *Enter name* MyRT => MyVPC => Create

## Config routes:

> Route Tables => *Choose MyRT* => *Routes tab* Edit routes => Add route => *Destination* 0.0.0.0/0 => *Target* Internet Gateway => MyIGW => Save routes
