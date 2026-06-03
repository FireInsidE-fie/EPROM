---
tags:
  - protocol
  - networking
abbreviation: LACP
---
Link Aggregation Control Protocol or LACP for short **provides a way to the bundling of multiple physical links into a single, logical link**.
It allows for multiple devices to negotiate an automatic bundling of links, through dedicated LACP packets.
# Advantages over Static Aggregation
LACP has **multiple advantages over using static aggregation**:
- Fail over occurs automatically, which hides potential link failures to peers of the link aggregation
- Configuration can be done dynamically, simplifying the setup of link aggregation
  It also allows individual devices to confirm that their peer will be able to handle aggregation
# Resources
- [Wikipedia Article on Link Aggregation](https://en.wikipedia.org/wiki/Link_aggregation#Link_Aggregation_Control_Protocol)