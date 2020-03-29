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
