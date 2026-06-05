---
tags:
  - tool/security
---

# Cheat Sheet
```sh
# Encrypt a file symmetrically using AES256
openssl aes-256-cbc -e -in message.txt -out encrypted-message.txt
# Decrypt a file symmetrically using AES256
openssl aes-256-cbc -d -in encrypted-message.txt -out original-message.txt
# Use PBKDF2 with a 10000 iterations
openssl aes-256-cbc -pbkdf2 -iter 10000 -e -in message.txt -out encrypted-message.txt
```