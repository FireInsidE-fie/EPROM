---
tags:
  - hardware
---
A networking device that **connects multiple devices to the same network**.
Switches are more efficient than the lesser hubs or repeaters.
Switches can operate at both layer 2 or 3 of the [[OSI Model]]. This is exclusive though, it can only operate on one layer at a time.
# How Do They Work
- A switch's main function is handling of incoming network packets and redirecting them to the appropriate destination device according to the [[IP Address]] found in the packet header.
- They keep track of what device is connected to each port, so they can send each packet to its destination directly instead of broadcasting it to everyone that's connected (what a hub would do).
## Trunk Ports
Trunk ports are **special ports carrying packets for multiple [[Virtual LAN]]s, usually to another switch**.
# Physical Structure
Switches can have a number of ports, ranging but not limited to 4, 8, 16, 24, 32, 64 for devices to plug into.
# Switch Stacking
Switch stacking is the process of **treating multiple physical switches as one logical switch**.
In such a setup, the switches are **controlled by a single management interface**.
This makes it easier to manage the switches, including configuration and monitoring. It also adds redundancy.
Stacking works best **when the switches are physically close**.
## How to Set up Switch Stacking
Concretely, **a stack consists of multiple switches that are physically connected** using special *stacking cables*, or built-in *stacking ports*.
One switch becomes the *master*, providing the main interface for, and managing, the entire stack.
If the master switch fails, another takes over.
## Vendor Lock-In
**Each switch vendor provides their own stacking technology**:
- Cisco has Stackwise or Virtual Switching System (VSS)
- Aruba has Virtual Switching Framework (VSF)
- Dell has Virtual Link Trunking (VLT)
- Juniper has Virtual Chassis
## Switch Stacking Vs Link Aggregation
Switch Stacking can easily be contrived with Link Aggregation, for example with [[Link Aggregation Group]]s or [[Link Aggregation Control Protocol]].
Each have their own use-cases though:
- Use Switch Stacking for unified switch management, and link aggregation for bandwidth increase and redundancy
- Switch Stacking makes switches act as one, while link aggregation does this to individual ports
- Switch stacking adds redundancy to switches, while link aggregation adds redundancy to ports/links
**Many networks use both approaches to guarantee redundancy across both switches and individual links**.
- [ ] 
# Resources
- [Cycle article on Switch Stacking](https://cycle.io/learn/switch-stacking-vs-link-aggregation)