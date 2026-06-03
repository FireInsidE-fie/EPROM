---
tags:
  - concept
  - networking
---
VLANs or Virtual [[Local Area Network]]s allow specific **devices within a network to be virtually split up**.
Virtual LANs are types of [[Broadcast Domain]]s.
This separation occurs at the [[OSI Model]]'s layer 2, *data link*.
It being at layer 2 means that it's the [[Switch]]'s job to enforce VLANs: it only routes data from a VLAN to other members of that same VLAN.
# Benefits
VLANs also makes it possible for **devices connected to different switches to share the same subnet**.
This is way easier than physically rewiring nodes to reflect how you want them to be grouped.
Instead, you just set their VLAN through software, saving you countless hours and tears.
This network separation also provides security because it **prevents devices in different VLANs from talking to each other**.
Even if two devices use the same physical cable, if their VLANs don't match, they can't talk together directly.
# VLAN Tagging
VLANs work by applying *tags* to network frames, which are then transmitted within the broadcast domain.
This effectively **splits the network** into separate, smaller sub-networks.
This is a nice way to keep network applications separated, while **still using the same physical media** (cables and networking devices) already deployed.
