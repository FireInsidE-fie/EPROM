---
tags:
  - tool/security
---

# Cheat Sheet
## Key Generation
### RSA
```sh
# Generate a RSA private key with 2048 bits
openssl genrsa -out private-key.pem 2048
# Get the public key for a private key
openssl rsa -in private-key.pem -pubout -out public-key.pem
# See details of a private key
openssl rsa -in private-key.pem -text -noout

# Encrypt
openssl pkeyutl -encrypt -in plaintext.txt -out ciphertext -inkey public-key.pem -pubin
# Decrypt
openssl pkeyutl -decrypt -in ciphertext -inkey private-key.pem -out decrypted.txt
```
### Diffie-Hellman
```sh
# Create a private key with 2048 bits
openssl dhparam -out dhparams.pem 2048
# Look inside
openssl dhparam -in dhparams.pem -text -noout
```
## Encryption
```sh
# Encrypt a file symmetrically using AES256
openssl aes-256-cbc -e -in message.txt -out encrypted-message.txt
# Decrypt a file symmetrically using AES256
openssl aes-256-cbc -d -in encrypted-message.txt -out original-message.txt
# Use PBKDF2 with a 10000 iterations
openssl aes-256-cbc -pbkdf2 -iter 10000 -e -in message.txt -out encrypted-message.txt
```