---
tags:
  - concept
  - networking
abbreviation: LAG
---
Link Aggregation allows **multiple physical links to be combined into one logical connection**.
This **increases bandwidth and adds redundancy** by preventing single-link failures from breaking the whole connection.
A variety of terms can refer to link aggregation: *trunking*, *bundling*, *bonding*, *channeling*, or *teaming*.
# How It Works
You create a LAG by **configuring a [[Switch]] to group multiple [[Ethernet]] links into one virtual link**/
Thus, **traffic is distributed across all active links**, which boost network capacity.
One link failing means the data is simply sent through other available links.
# Static Vs Dynamic Aggregation
Compared to [[Link Aggregation Control Protocol]], LAG is more statically configured.
LACP allows one to dynamically configure and manage links, while raw LAGs are more hands-on.
This makes it **best for small, stable setups**, while LACP is perfect for scalable and redundant networks.
# Resources
- [cycle.io article on Link Aggregation](https://cycle.io/learn/switch-stacking-vs-link-aggregation#what-is-link-aggregation-lag)
- [Wikipedia Article on Link Aggregation](https://en.wikipedia.org/wiki/Link_aggregation)