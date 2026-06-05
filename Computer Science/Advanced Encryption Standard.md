---
tags:
  - algorithm
  - cryptography
abbreviation: AES
---
DES was published by the [[National Institute of Standard and Technology]] or NIST in 2001.
It is a [[Symmetric Encryption]] algorithm that uses a **key of 128, 192 or 256 bits**.
It is **still considered secure and in widespread use to this day**.
# How It Works
AES **repeats the following four transformations** multiple times:
1. `SubBytes(state)`: This transformation looks up each byte in a given *substitution table (S-box)* and **substitutes it with the respective value**. The `state` is 16 bytes, i.e., 128 bits, saved in a 4 by 4 array.
2. `ShiftRows(state)`: The second row is **shifted** by one place, the third row is shifted by two places, and the fourth row is shifted by three places. This is shown in the figure below.
3. `MixColumns(state)`: Each column is **multiplied by a fixed matrix** (4 by 4 array).
4. `AddRoundKey(state)`: A **round key is added to the state** using the XOR operation.
![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/049bad7deb4e6dd426335d7c3477f10a.png)
The number of transformation sequences performed **depends on the key size**.
# Resources
- [AES Standard](https://csrc.nist.gov/publications/detail/fips/197/final)