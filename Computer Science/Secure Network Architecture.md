---
tags:
  - concept
  - security
---
News flash! Designing a network securely is important.
A well-designed network has internet usage, device communication, but also redundancy, optimization, and security.
# Network Segmentation
[[Subnet]]s are a nice **organizational tool, but aren't enough in a security way**. Any one device doesn't have restrictions as to where it could connect. Subnets only subdivide a network, but don't enforce any further restrictions.
Imagine someone brings their laptop from home; they could connect to any one subnet as they move around the premises. Now, imagine if that laptop has a trojan on it... yikes.
## VLANs
[[Virtual LAN]]s are used to **segment portions of a network at layer two, and differentiate devices**.
VLANs are **configured on a [[Switch]] by adding a *tag* to a frame.**
## Security Zones
Security Zones **define what or who is in a VLAN, and what goes in and out**.
### Commonly Standardized Zones
Here is a list of some of the most commonly seen zones in professional networks.
- **External**: All devices and entities outside our network
- **DMZ**: Separates untrusted networks or devices from our internal resources
- **Trusted**: Internal networks or devices. Here, there is no confidential or sensitive information
- **Restricted**: High-risk stuff, servers, databases
- **Management**: Less commonly seen, often merged with audit. Has devices or services dedicated to network or device management.
- **Audit**: Devices and services dedicated to security or monitoring. Can be grouped with management.
# Policies
Segmentation and architecture are both great things, and very important for security. **But how do you decide what actually gets enforced?** Enter policies.
## Access Control Lists
ACLs are used as **a set of rules for access control protocols and applications**. They define what rules get enforced on that level, whether "that level" means a [[Router]], a [[Firewall]], or something else entirely.
ACLs contain *Access Control Entries* (basically just rules) that define the criteria for accepting or refusing traffic. They determine the action, as well as the destination/source address and port, which could be ranges.
Once defined, ACLs can be **used for vendor-specific implementations**. For example, [[Cisco]] uses them for traffic filtering, priority, or custom queuing, and dynamic access control.
## Zone-Pair
Zone-pairs are **direction-based rules that define what traffic can come from one VLAN to the next**. So, from one zone to another; hence "zone-pair".
For example, you'll define the traffic allowed to come from the DMZ to the LAN, or vice versa.
These rules are **defined in your network's [[Firewall]]**.
Ideally, you'll have your firewall act as the gates between all of your zones, and define zone-pairs for every pair of zone possible.
You can **define what services will be allowed to hop from one zone to the other**. Best use a white-list instead of a black-list here!
# Validating Network Traffic with SSL Inspection
SSL inspection is **the act of using an SSL proxy to intercept traffic and decrypt it**.
The proxy will then send the decrypted data to a Unified Threat Management system, or UTM, which will verify that the traffic isn't one from a threat actor having compromised an internal machine.
This is mainly useful to be able to **check the traffic that we've already authorized through zone-pairs and other means**. Rules are fine to define what services go through where, but that doesn't check the actual contents of those connections, which is what SSL inspection is for.
This approach has drawbacks, however. **You have to intercept everything a la [[Man in The Middle Attack]] through a proxy** to check what's inside the packets.
# Mitigations to Common Attacks
## DHCP Snooping
[[Dynamic Host Configuration Protocol]] snooping is a **feature that acts like a [[Firewall]] between untrusted hosts and trusted DHCP servers**.
It was created to fight against rogue DHCP server; **its job is to validate and rate-limit DHCP traffic**, especially for untrusted hosts.
DHCP snooping operates at layer two, on the [[Switch]], despite DHCP being layer 3.
The switch will **store info about the active hosts in a *DHCP Binding Database*, setting untrusted hosts as it needs**.
There are multiple conditions the protocol will inspect to check whether a DHCP packet should be dropped:
- It arrived from outside the network
- The [[MAC Address]] and DHCP client hardware address don't match
- A new interface is used for `DHCPRELEASE` or `DHCPDECLINE`
- The packet includes a relay agent that is not `0.0.0.0`
## Dynamic ARP Inspection
[[Address Resolution Protocol]] inspection's goal is to **validate ARP packets in a network**.
It will **validate and rate-limit ARP packets as necessary, for example if its MAC and [[IP Address]] don't match**.
It can intercept, log and discard packets as needed.
ARP inspection **uses the DHCP binding database of a switch, filled by DHCP snooping**.
In short, **DHCP snooping sets the untrusted IPs and MACs, and ARP will check the pair for mismatches in the ARP packets, and drop them if that's the case**.