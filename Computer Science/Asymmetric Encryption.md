---
tags:
  - concept
  - cryptography
---
Asymmetric Encryption or Public-key Cryptography is the **process of creating a secure communication between two parties using a combination of a public and a private key**.
It is called *asymmetric encryption* because it uses a different key for encryption and decryption.
This is in stark contrast to its counterpart [[Symmetric Encryption]].
# How It Works
When establishing communications, two parties using the public-key cryptography paradigm will do a simple but intricate exchange of encrypted information:
- The server creates a private and public key that is going to be used for communications.
- As its name implies, the public key is broadcast to anyone that wants to talk with the server securely.
- Any client that wants to talk to the server can encrypt their packets using the public key.
  **Only the private key the server holds can decrypt those messages, so even the client that just encrypted them cannot read them anymore at this point.**
- The server receives those messages and, thanks to the private key it kept, can decrypt them.
## Whispering So You Can Talk Later On
Since asynchronous encryption like using a public/private key pair is a bit slow to use (key sizes usually fall in the kilobits!), **servers typically use them only to exchange a synchronous encryption key** that is then going to be used for all future communications.
This is how protocols such as HTTPS establish their communications and keep a fast rate of transfer going!
## Confirming I Am Who I Am
Asymmetric encryption has more uses that simple confidentiality.
Suppose you revert the roles: you **encrypt your message** using your private key, and anyone with your public key can decrypt it.
So much for confidentiality, right? Well, instead of confidentiality, this ensures **authenticity, integrity, and non repudiation**.
**In effect, decrypting your message using your public key shows that it indeed came from you**.

# Examples
- [[Rivest-Shamir-Adleman]] (RSA)
- [[Diffie-Hellman]]
- [[Transport Layer Security]]
- [[Secure Sockets Layer]]
- [[HTTPS]]
- Many, many more...
# Resources
- 