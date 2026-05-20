---
tags:
  - tool/security
  - windows
---
CAPA or Common Analysis Platform for Artifacts is **a tool used for static analysis of executables**.
It uses [[YAML]] rules to match malware behavior and report it.
# Cheat Sheet
```powershell
# Run CAPA on a specific binary
capa .\binary.bin

# Display help
capa /h

# Use verbose or extra verbose for results
# Extra verbose is useful to detail why a given CAPA rule was matched
capa .\binary.bin /v
capa .\binary.bin /vv

# Output results as JSON
capa .\binary.bin /v /j
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
## Namespace
CAPA **uses namespaces to group items with the same purpose**.
Namespaces are often nested, with top-level namespaces or TLNs containing more precise namespaces as you go down their levels.
Namespaces are often **linked to capabilities**, which are the actual actions taken by malware, classified by namespace.

> [!INFO] On Nursery rules
> Nursery rules are CAPA rules that aren't quite polished just yet.
> Look at that folder in the CAPA namespaces organization repo when you don't find the rule you're looking for in the folder that CAPA references.

# Resources
- [capa GitHub Repository](https://github.com/mandiant/capa)
- [CAPA namespace organization](https://github.com/mandiant/capa-rules/blob/master/README.md#namespace-organization)
- [MBC Summary](https://github.com/MBCProject/mbc-markdown/blob/main/mbc_summary.md)
- [CAPA Explorer Web](https://mandiant.github.io/capa/explorer/#/)