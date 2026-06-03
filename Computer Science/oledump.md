---
tags:
  - tool/forensics
  - security
---
`Oledump.py` is a Python tool made to **analyze [[Object Linking and Embedding]] OLE2 files**.
It is used to extract and examine the contents of OLE2 files.
# Cheat Sheet
```sh
oledump.py file.xlsm

# Select the 4th data stream found
oledump.py file.xlsm -s 4

# Decompress VBA macros foudn inside the given stream
oledump.py file.xlsm -s 4 --vbadecompress
```
# Data Streams
Data streams **define the type of the contents of a given OLE2 file**.
When analyzing a file with `Oledump.py`, data streams will be indexed with numbers.
```
ubuntu@10.113.181.70:~/Desktop/tasks/agenttesla$ oledump.py agenttesla.xlsm
A: xl/vbaProject.bin
 A1: 468 'PROJECT'
 A2: 62 'PROJECTwm'
 A3: m 169 'VBA/Sheet1'
 A4: M 688 'VBA/ThisWorkbook'
 A5: 7 'VBA/_VBA_PROJECT'
 A6: 209 'VBA/dir'
```
In the example above, a [[Visual Basic]] script was found and indexed using the letter `A`.
Then, all underlying data streams of that script were indexed using numbers.
## Special Data Streams
- `M` means there is a macro, which might be of special interest.
- `m`