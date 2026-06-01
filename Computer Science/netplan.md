---
tags:
  - tool/network
  - linux
---
Netplan is a **declarative configuration tool**, allowing easy management of network configuration for a given host.
It is essentially **an abstraction layer for configuring networking backends**.
It can use two backends: [[systemd-networkd]] for servers, or [[NetworkManager]] for desktop systems.
It uses [[YAML]] for its configuration files, usually stored in `/etc/netplan/`.
# Cheat Sheet
## Configuration
### Example - Simple Static IP
```yaml
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: false
      addresses:
        - 192.168.1.9/24
      routes:
        - to: default
          via: 192.168.1.254
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]
```
# How It Works
The `netplan` service is **essentially a wrapper around a networking backend** that does the actual job. Backends are sometimes called *renderers*.
The delegation of that networking job **happens during early boot**, where Netplan's *network renderer* reads the configuration, and sets the config of the appropriate backend.
# Sources
- `man netplan(5)`
- 