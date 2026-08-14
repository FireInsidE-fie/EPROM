---
tags:
  - concept
  - networking
abbreviation: VLAN
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
Often, you tag frames by **setting an access port on an interface to a specific VLAN number**. Then, the [[Switch]] will tag the frame appropriately as per your configuration.
In memory, the frames are associated with a VLAN ID before they are sent out over the wire.
## 802.1 Tag
The 802.1 or dot1q tag will **designate the VLAN that the traffic originated from**.
It is a **standard that many different switches can interpret**.
# Native VLAN
The native VLAN is **the VLAN that is chosen when a frame arrives without a tag**.
Essentially, it is the switch's **default VLAN**.
If a frame is of the native VLAN, it **enters and leaves the switch untagged**.
# Routing Between VLANs
VLANs, inherently, split a network in segments. By default, a device with access to an interface tagged 10 can't communicate with one on 20. So, how does one route between distinct VLANs?
Usually, routing between VLANs is **achieved by connecting a [[Switch]] and a [[Router]]**. This design is called ROAS, or Router On A Stick.
VLANs are then **configured to communicate through a specific interface of the switch, known as the *switch port*.** This connection is known as the *trunk*. Since all data go through this connection, it is called "on a stick".
The router is then responsible of doing the actual "routing" (crazy, right?) for the frames it receives.
It checks its routing table, and **tags the frames with the new VLAN tag, so the switch knows where to forward it next**.
The switch then checks its MAC table for that specific VLAN, and sends the frame according to its destination header.