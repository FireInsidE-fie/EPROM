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
