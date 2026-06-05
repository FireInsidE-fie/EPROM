---
tags:
  - concept
  - cryptography
---
A symmetric encryption algorithm **uses the same *key* for encryption and decryption**.
# Types of Symmetric Encryption Algorithms
- [[Substitution Cipher]]
- [[Transposition Cipher]]
- Block Cipher: These ciphers convert the plaintext into blocks and encrypt each block.
  A block is usually 128 bits, represented in 16 bytes and represented in a 4 by 4 array.
  This block is then fed to the encryption algorithm for encryption.
  ![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/2d69973a4fbf8220e64c3e896841b21d.png)
- Stream Cipher: These ciphers **encrypt the plaintext byte by byte** instead of by blocks of bytes.
# Tools
There are many programs used for asymmetric encryption.
- [[GNU Privacy Guard]]
- [[OpenSSL]]
# Limitations
Limitations of symmetric encryption algorithms are fixed by [[Asymnetric Encryption]].
## Scalability
Symmetric Encryption algorithms are, by design, **not scalable**.
For each party in a conversation, you'd need a separate key, and a secure way to share them with all parties involved.
# Examples
- [[Data Encryption Standard]]
- [[Advanced Encryption Standard]]
- [[International Data Encryption Algorithm]] (IDEA)
- [[Triple DES]]
- [[CAST5]]
- [[BLOWFISH]]
- [[TWOFISH]]
- [[CAMELLIA]]