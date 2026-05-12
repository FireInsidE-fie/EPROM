---
tags:
  - networking
  - protocol
abbreviation: FC
---
Fibre Channel is a **high-speed data transfer protocol used to connect storage to servers in [[Storage Area Network]]s**.
It is most often seen through and between commercial data centers.
Fibre Channel is called this way because it **usually runs on [[Optical Fiber]] cables**.
It provides **lossless, in-order delivery of data**, but isn't very useful with another protocol on top of it, like [[Small Computer System Interface]] (in the form of [[Fibre Channel Protocol]].
# Fibre Channel Layers
Fibre Channel has its own **layering system** to define how data is transmitted.
- FC-0: The physical layer, cables, connectors, etc.
- FC-1: The transmission layer, decoding/encoding
- FC-2: The network layer, port to port connections
- FC-3: The common services layer, for encryption, RAID, etc.
- FC-4: The protocol layer, where SCSI, iSCSI, FCP etc. live.