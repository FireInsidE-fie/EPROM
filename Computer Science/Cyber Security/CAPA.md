---
tags:
  - tool/security
  - windows
---
CAPA or Common Analysis Platform for Artifacts is **a tool used for static analysis of executables**.
# Cheat Sheet
```powershell
# Run CAPA on a specific binary
capa .\binary.bin

# Display help
capa /h

# Use verbose or extra verbose for results
capa .\binary.bin /v
capa .\binary.bin /vv
```
# Breakdown of Results
Results of a CAPA analysis can be pretty complicated, so here is a breakdown of the structure.
## First Block
The first block contains basic information about the file. This includes the following:
- The cryptographic algorithms, such as the `md5`, and `sha1/256`.
- The `analysis` field tells us how CAPA performed its analysis on the file.
- The `os` field reveals the operating system (OS) context for which the identified capabilities apply.
- The `arch` field allows us to determine whether we are dealing with a binary related to x86 architecture.
- The `path` where the analyzed file was located.
## MITRE ATT&CK
Then comes a block identifying the attack tactic using the [[MITRE ATT&CK]] framework.
## MAEC
After that comes the MAEC analysis.
*Malware Attribute Enumeration and Characterization* is a specialized language using a set of defined attributes to describe malware.
Common attributes include *launcher* (launching additional payloads) or *downloader* (fetching new behavior from somewhere).
## MBC
Then, the *Malware Behavior Catalogue*. This one serves as **a repertoire of malware objectives and behaviors**.
These results are often used in tandem with ATT&CK labels, to add additional information.
# Resources
- [capa GitHub Repository](https://github.com/mandiant/capa)
- [MBC Summary](https://github.com/MBCProject/mbc-markdown/blob/main/mbc_summary.md)