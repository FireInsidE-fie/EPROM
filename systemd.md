---
tags:
  - Unix
  - Linux
---
A system and service manager for [[Linux]] [[Operating system]]s. It's usually run as the first [[Process]] as an init system that brings up and maintains user-space [[Service]]s.
Each logged in user has their own instance.

# How it works
systemd is usually installed as the `/sbin/init` [[symlink]] so that it's started during early boot.
When run as the system instance (not as a user's manager), it tries to read from the config file `system.conf` and all the files from the `system.conf.d` directories.
When run as a user instance, it interprets the `user.conf` and `user.conf.d` files and directories instead.[^1]
>**Extract from the systemd [[Linux]] manual :** systemd contains native implementations of various tasks that need to be executed as part of the boot process. For example, it sets the hostname or configures the loopback network device. It also sets up and mounts various API file systems, such as /sys/, /proc/, and /dev/.

[^1]: man 5 systemd-system.conf(5) on a [[Linux]] system
