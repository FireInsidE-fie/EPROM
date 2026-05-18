---
tags:
  - concept
  - programming
---
Memory, or Random Access Memory (RAM) is the main storage of memory for an operating system at runtime.
# Virtual Vs Physical Memory
Physical memory refers to the entire memory attached to the system, usually in the form or RAM sticks.
Virtual memory, on the other hand, refers to the part of that physical memory that is allocated for a singular process.
This gives the process the illusion it has access to the entire memory space, and allows it to freely use that virtual space as it pleases.
There's a translation layer between the virtual memory addresses and the physical, actual addresses on the RAM.
This translation barely has an impact on the read/write performance on RAM from the process' point of view, but it's important to know it's there.
# Checking the Memory Maps of a [[Process]]
`cat /proc/self/maps` prints out the list of maps used by the cat process you just created.
# Resources
[Wikipedia - Virtual Memory](https://en.wikipedia.org/wiki/Virtual_memory)