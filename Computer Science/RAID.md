---
tags:
  - concept
  - hardware
---
RAID is **a way to store data on more than one disk at a time**.
It coordinates between two or more storage devices, creating a *disk array* out of them.
This array is then used to distribute data across the storage devices, according to a configured strategy.
# Striping Vs Mirroring
## Striping
Striping is **the act of splitting a particular piece of data across multiple storage devices**.
This is particularly useful to **enhance throughput and latency**, as multiple parts of said data can be queried at the same time, on each storage device.
## Mirroring
Mirroring is **the act of duplicating data over several storage devices**.
This, while also potentially enhancing throughput, **creates redundancy for data**, creating an effective backup in case one of the storage devices fails.
# RAID Levels
RAID can be configured in a few different ways, defining the manner in which it will distribute the data in the storage it has access to.
These different configuration possibilities are called *RAID levels*.
**RAID levels define the amount of redundancy** that the disk array is going to provide.
This means they set the minimum number of drives they require, as well as performance, energy usage, fault tolerance, availability, etc.
## Standard RAID Levels
### RAID 0
RAID 0 is a **simple striping strategy**, which means the data is laid through all available storage devices in the RAID.
The main benefit of RAID 0 is **higher read/write speeds**, since the data is evenly distributed over all available drives.
Critically, **RAID 0 has no fault tolerance or redundancy**.
### RAID 1
RAID 1 is also simple: **disk mirroring**. All data is duplicated on each available drive.
This means that any drive in the RAID could answer a query for data, because each has the same exact state.
This means that **the slower drive is the one that limits performance**.
## Nested RAID Levels
Nested RAIDs are ones in which **multiple RAID levels are used**, to combine the capabilities of individual levels.
## RAID 10
RAID 10, also called RAID 1+0, is **a RAID 0 layered over RAID 1s**.
It combines mirroring and striping, effectively enjoying the benefits of both at the same time.
The data is **mirrored first, and then striped over other mirrors**. As such, it requires a **minimum of 4 disks**.
It is **the perfect RAID for high-throughput applications**, as it provides better read/write speeds and latency than all over RAID levels, except RAID 0.
# Resources
- [TechTarget article on RAID Levels](https://www.techtarget.com/searchstorage/answer/RAID-types-and-benefits-explained)