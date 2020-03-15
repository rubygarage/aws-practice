# VPC Security

## Security Group
---
### A security group acts as a virtual firewall for your instance to control inbound and outbound traffic. When you launch an instance in a VPC, you can assign up to five security groups to the instance. Security groups act at the instance level, not the subnet level. Therefore, each instance in a subnet in your VPC can be assigned to a different set of security groups.

#### The following are the basic characteristics of security groups for your VPC:

- You can specify allow rules, but not deny rules.

- You can specify separate rules for inbound and outbound traffic.

- When you create a security group, it has no inbound rules. Therefore, no inbound traffic originating from another host to your instance is allowed until you add inbound rules to the security group.

- By default, a security group includes an outbound rule that allows all outbound traffic. You can remove the rule and add outbound rules that allow specific outbound traffic only. If your security group has no outbound rules, no outbound traffic originating from your instance is allowed.

- **Security groups are stateful** — if you send a request from your instance, the response traffic for that request is allowed to flow in regardless of inbound security group rules. Responses to allowed inbound traffic are allowed to flow out, regardless of outbound rules.

- Instances associated with a security group can't talk to each other unless you add rules allowing the traffic (exception: the default security group has these rules by default).

Security groups are associated with network interfaces. After you launch an instance, you can change the security groups that are associated with the instance, which changes the security groups associated with the primary network interface (eth0). You can also specify or change the security groups associated with any other network interface. By default, when you create a network interface, it's associated with the default security group for the VPC, unless you specify a different security group. For more information about network interfaces, see Elastic Network Interfaces.

### Example of a SG to allow SSH connection to the instance:
<img src="https://i.imgur.com/tAnBPqK.png"/>
<img src="https://i.imgur.com/jX2dI2w.png"/>


<br>

## Network Access Control List (ACL)
---
### A network access control list (ACL) is a layer of security for your VPC that acts as a virtual  firewall for controlling traffic in and out of one or more subnets. You might set up network ACLs with rules similar to your security groups in order to add an additional layer of security to your VPC.

- rule is either INBOUND or OUTBOUND
- rule can specify ALLOW or DENY
- inbound rule has SOURCE CIDR
- outbound rule has DESTINATION CIDR

#### Default Network ACL allows all inbound and outbound traffic.

### The following are the parts of a network ACL rule:

- **Rule number.** Rules are evaluated starting with the lowest numbered rule. As soon as a rule matches traffic, it's applied regardless of any higher-numbered rule that might contradict it.

- **Type.** The type of traffic; for example, SSH. You can also specify all traffic or a custom range.

- **Protocol.** You can specify any protocol that has a standard protocol number. For more information, see Protocol Numbers. If you specify ICMP as the protocol, you can specify any or all of the ICMP types and codes.

- **Port range.** The listening port or port range for the traffic. For example, 80 for HTTP traffic.

- **Source.** [Inbound rules only] The source of the traffic (CIDR range).

- **Destination.** [Outbound rules only] The destination for the traffic (CIDR range).

- **Allow/Deny.** Whether to allow or deny the specified traffic.