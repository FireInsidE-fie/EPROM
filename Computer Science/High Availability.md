---
tags:
  - concept
abbreviation: HA
---
High Availability or HA is a **design principle that ensures that a system can undergo some amount of failure, and still retain its required performance**.
In effect, this often translates to having redundant or replicated services, in case one goes down.
# How It Works
## Clusters
HA clusters are **groups of hosts that work together to keep applications running with little to no downtime**.
The idea is to provide a single access point, and allow a single system to take over in case another one fails.
## Load Balancing
Load balancing involves distributing the load across multiple systems, to ensure that no single system is overloaded with requests.
## Failover
Failover is a process that **allows a service to switch to backup system if the primary system fails**.
# High Availability Vs Fault Tolerance
HA and fault tolerance are both design principles that take failure into account. Still, they are meaningfully different.
Fault tolerance **expands on high availability and offers a greater level of protection in case of failures**.
Essentially, fault tolerance is HA with more standards. Even less, or no downtime at all, is expected.
Of course, **fault tolerance usually costs more in time, effort, and money to put into place** as a result.
# High Availability Vs Disaster Recovery
Disaster recovery deals with system-wide failures, which means that it operates on a higher level than HA.
It **makes sure that processes are in place in case of a systemwide failure**, while HA focuses on individual components.
# Resources
- [Traefik Labs Docs on High Availability](https://traefik.io/glossary/understanding-high-availability)