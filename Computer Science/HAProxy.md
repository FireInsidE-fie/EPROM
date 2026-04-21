---
tags:
  - tool/network
---
HAProxy is a **general-purpose TCP/HTTP [[Load Balancer]] and [[Reverse Proxy]].**
It can provide load balancing at both layer 4 for [[Transmission Control Protocol]], and layer 7 for [[HyperText Transfer Protocol]].
# Configuration
Configuration in HAProxy for a proxy configuration specifically works through *frontends and backends*.
Frontends are **sets of listening sockets accepting client connection**.
Backends are **descriptions of servers to which HAProxy will forward connections**.
You link frontends and backends to determine how to distribute connections.