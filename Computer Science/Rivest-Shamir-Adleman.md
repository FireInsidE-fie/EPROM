---
tags:
  - algorithm
  - cryptography
abbreviation: RSA
---
RSA or the Rivest-Shamir-Adlman algorithm is a **[[Asymmetric Encryption]] algorithm that enables secure data transmission over insecure channels**.
The general idea is to exploit the loophole that **while multiplying two numbers is easy, figuring out which numbers were used in a multiplication with a final result isn't**.
# How It Works
1. Start by choosing two random prime numbers, $p$ and $q$.
   Calculate $N = p \times q$ .
2. Choose two integers $e$ and $d$ so that $e \times d = 1 \mod{\phi(N)}$, where $\phi(N) = N - p - q +1$.
   This will help us with generating the public key ($N$, $e$) and private key ($N$, $d$).
3. The sender can now encrypt a value $x$ by calculating $y = x^e \mod N$.
4. The recipient can then decrypt $y$ by calculating $x = y^d \mod N$.
   Worth noting that $y^d = x^{ed} = x^{k\phi(N)+1} = (x^{\phi(N}))^k \times x = x$.
The security is based on the fact that **given $p$ and $q$, it's easy to find $N$, but it's tough finding $p$ and $q$ given $N$**.
# Resources
- https://github.com/Ganapati/RsaCtfTool
- https://github.com/ius/rsatool