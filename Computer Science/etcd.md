---
tags:
  - tool
---

etcd is a **key-value store for sharing data between hosts**.
It allows you to **read and write values using [[HyperText Transfer Protocol]]**.
It can also **send out notifications when watched values change**, making it perfect for sharing key-value pairs between hosts.
# The Raft Algorithm
Raft is a *consensus algorithm*, which is a system for making different machines **agree on state changes across a cluster**.
It works by assigning an *elected leader*, and making all the other nodes in the cluster (*followers*) follow its lead, so to speak.
The leader is **responsible for log replication to the followers.**
