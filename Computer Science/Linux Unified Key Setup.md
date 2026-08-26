---
tags:
  - security
  - encryption
abbreviation: LUKS
---
# Partition Structure
When a partition is encrypted with LUKS, the disk layout looks a little bit like this:

| LUKS phds | KM1 | KM2 | ... | KM8 | Bulk Data |
| --------- | --- | --- | --- | --- | --------- |
- **LUKS phdr**: Stands for *LUKS Partition Header*. It stores information about the UUID, the used cipher, the cipher mode, the key length, as well as the checksum of the master key.
- **KM**: KM stands for *Key Material*. There are multiple, each associated with a key slot, which can be indicated as active in the partition header. When a key slot is active, the associated key material starts storing the master key, encrypted with a user's password.
  You could have user 1 using slot 1, and thus having the master key encrypted with their password on KM1. Then a second user using slot 2, and that would mean M2 stores the same master key, but encrypted with a different password.
- **Bulk Data**: The data encrypted by the master key.
# Mechanism
LUKS **reuses existing block encryption implementations**.
## Syntax
```c
enc_data = encrypt(cipher_name, cipher_mode, key, original, original_length)

original = decrypt(cipher_name, cipher_mode, key, enc_data, original_length)
```

