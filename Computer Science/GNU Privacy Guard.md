---
tags:
  - tool/security
abbreviation: GnuPG, GPG
---
GPG is a tool that **implements the [[OpenPGP]] standard**.
# Cheat Sheet
```sh
# Check supported ciphers
gpg --version

# Encrypt a message using symmetric cryptography in binary OpenPGP format
gpg --symmetric --cipher-algo <algorithm> message.txt
# Output as armored aSCII instead of OpenPGP
gpg --armor --symmetric --cipher-algo <algorithm> message.txt

# Decrypt an AES256 message
gpg --decrypt --symmetric message.txt
```
