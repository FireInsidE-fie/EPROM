This note documents the tagging system used in this vault — the available tags, what each means, and the design decisions behind them.
# Conventions
Tags use `snake_case` for multi-word names. Nested tags use a `/` separator (e.g. `tool/security`). Every note gets one **type tag** and, where applicable, one or more **domain tags**.
# Type Tags
These describe what kind of thing a note is.

| Tag              | Meaning                                                                                                                                                                                                                  |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `concept`        | An abstract idea or mechanism — something you learn rather than use directly. Recursion, OSI Model, Virtual Memory.                                                                                                      |
| `protocol`       | A communication or interaction standard between two parties. HTTP, SSH, Kerberos.                                                                                                                                        |
| `algorithm`      | A defined procedure for solving a problem. Quicksort, RSA, Caesar Cipher.                                                                                                                                                |
| `data_structure` | A way of organising data in memory. Linked List, Stack, Hash Map.                                                                                                                                                        |
| `tool`           | Software you run or use directly. Can be nested — see below.                                                                                                                                                             |
| `vulnerability`  | A class of weakness that exists in a system. XSS, IDOR, SQL Injection.                                                                                                                                                   |
| `attack`         | A technique actively used to exploit a system. Reverse Shell, CSRF, Command Injection. A note can carry both `vulnerability` and `attack` if it describes both the weakness and its exploitation.                        |
| `standard`       | A formal specification — typically an RFC, ISO standard, or W3C spec. X.509, JWT, ELF, URI. Note that protocols are also standards, but the `protocol` tag is used when the communication aspect is the primary framing. |
| `encoding`       | A scheme for representing data. Base64, Unicode.                                                                                                                                                                         |
| `hardware`       | Physical computing components or hardware-level interfaces.                                                                                                                                                              |
| `organization`   | A notable institution or foundation. OWASP, Free Software Foundation.                                                                                                                                                    |
## Tool Subtags
`tool` is nested when the tool's domain is specific enough to be worth filtering on:

| Tag             | Meaning                                                                        |
| --------------- | ------------------------------------------------------------------------------ |
| `tool/security` | Offensive or defensive security tools. Nmap, Metasploit, Burp Suite, Fail2Ban. |
| `tool/network`  | Network infrastructure tools. nginx, Wireshark, tcpdump.                       |
| `tool/editor`   | Text editors. vim, nvim, nano.                                                 |
| `tool/compiler` | Compilers and compiler toolchains. GCC, clang, LLVM.                           |
For tools that don't fit a subcategory clearly, the flat `tool` tag is used.
## Standard Subtags

| Tag                    | Meaning                                                           |
| ---------------------- | ----------------------------------------------------------------- |
| `standard/file_format` | Binary or structured file format specifications. ELF, Mach-O, PE. |
# Domain Tags
These describe the field a note belongs to. Used alongside type tags to enable cross-cutting queries.

| Tag            | Meaning                                                                                                             |
| -------------- | ------------------------------------------------------------------------------------------------------------------- |
| `linux`        | Linux or Unix-specific concepts and tooling.                                                                        |
| `windows`      | Windows-specific concepts and tooling.                                                                              |
| `networking`   | Network layer concepts, protocols, and tools.                                                                       |
| `security`     | Cybersecurity domain — attacks, defences, tools, and concepts.                                                      |
| `cryptography` | Cryptographic primitives, protocols, and implementations.                                                           |
| `programming`  | Writing, compiling, or reasoning about code.                                                                        |
| `database`     | Database systems and related tooling.                                                                               |
| `hardware`     | Used both as a type tag and as a domain tag for notes that are hardware-adjacent without being hardware themselves. |
# Why Both `tool/security` And `security`?
Obsidian's nested tag search works top-down: searching `#tool` matches all `tool/*` subtags, but searching `#security` does **not** match `tool/security`.
To keep "show me everything security-related" as a single query, security tools carry both `tool/security` and the flat `security` domain tag. The redundancy is intentional.
# Deprecated Folders
Notes in `Books (deprecated)/` and `Tutorials (deprecated)/` carry `book` and `tutorial` tags respectively. These folders are winding down and their tags are not part of the active taxonomy.
