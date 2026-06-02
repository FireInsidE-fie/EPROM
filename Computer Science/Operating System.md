---
tags:
  - concept
abbreviation: OS
---
An operating system is **software that sits between applications and a computer's hardware**.
It provides useful abstractions for other software to be able to interface and make use of the host's hardware.
# Responsibilities
Operating Systems have a wide array of roles, including:
- [[Process]] Management
- [[Memory]] Management
- [[File System]] Management
- User Management
- Device Management
# Privilege Layers
In order to not allow every single software running on the host to have full access to the hardware resources, **operating systems usually divide privileges in two layers**.
This enhances security and stability of the system by not entrusting its fate to user space applications.
## Kernel Space
The privileged, highly locked-down core of the OS.
This is, appropriately, **where the [[Kernel]] runs**.
It has **unrestricted access to the [[Processor]], [[Memory]] and all other hardware components**.
## User Space
User Space is **where standard user applications will run**.
Here, you can't access hardware resources directly, instead relying on abstractions the kernel will give you, called *system calls*.
