---
abbreviation: IP
tags:
  - networking
  - protocol
---
Responsible for relaying packets across networks, routing data between different machines.
It looks at a packet's header to know which host to target it towards.
Part of the [[Internet Protocol Suite]].
# Datagrams
Datagrams is basically another word for network packet.
A datagram is composed of two sections: a header and a payload.
The header is composed of many things:
- The source [[IP address]]
- The destination [[IP address]]
- Other metadata needed to route and deliver the packet
# Addressing methods
There are four ways for a packet to be addressed to hosts:
## Unicast
As the name would suggest, target a single host as the receiver.
## Broadcast
Target all the nodes in the network scope defined in the packet header. Usually an entire network [[Subnet]].
## Multicast
Mostly like broadcast but targets only a subset of the nodes in a network instead of all of them.
## Anycast
Same as multicast, but only sends the packet to the closest node of the subset.
# Resources
[Wikipedia](https://en.wikipedia.org/wiki/Internet_Protocol)