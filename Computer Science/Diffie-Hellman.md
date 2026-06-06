---
tags:
  - algorithm
  - cryptography
---
Diffie-Hellman is a **key-exchange algorithm leveraging [[Asymmetric Encryption]] to safely exchange a secret between two parties**.
This secret is very often a symmetric key to be used for secure communications.
# How It Works
Here are the key steps:
1. Alice and Bob agree on the **public variables**: a large prime number $p$ and a generator $g$, where $0 < g < p$. These values will be disclosed publicly over the communication channel. Although insecurely small, we will choose $p = 29$ and $g = 3$ to simplify our calculations.
2. Each party chooses a private integer. As a numerical example, Alice chooses $a$ = 13, and Bob chooses $b$ = 15. Each of these values represents a **private key** and must not be disclosed.
3. It is time for each party to calculate their **public key** using their private key from step 2 and the agreed-upon public variables from step 1. Alice calculates $A$ = $g$ * $a$ mod $p$ = 313 mod 29 = 19 and Bob calculates $B$ = $g$ * $b$ mod $p$ = 315 mod 29 = 26. These are the public keys.
4. Alice and Bob send the keys to each other. Bob receives $A$ = $g$ * $a$ mod $p$ = 19, i.e., Alice’s public key. And Alice receives $B$ = $g$ * $b$ mod $p$ = 26, i.e., Bob’s public key. This step is called the **key exchange**.
5. Alice and Bob can finally calculate the **shared secret** using the received public key and their own private key. Alice calculates $B$ * $a$ mod $p$ = 2613 mod 29 = 10 and Bob calculates $A$  * $b$ mod $p$ = 1915 mod 29 = 10. Both calculations yield the same result, $g$ * $a$ * $b$ mod $p$ = 10, the shared secret key.
