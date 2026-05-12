---
tags:
  - standard

---
X.509 is an [[International Telecommunication Union]] standard **defining the format of public key [[Certificates]]**.
X.509 are **used in many modern Internet protocols**, such as [[Transport Layer Security]]/[[Secure Sockets Layer]], which is the basis for [[HTTPS]].
# Concept
A X.509 *certificate* **binds an identity to a public key, which contains a digital signature**.
A certificate contains an *identity*, such as a [[Hostname]], an organization, or even and individual, as well as a *public key*.
It is either signed by a *Certificate Authority* or is *self-signed*.
When a certificate is signed by a **trusted certificate authority**, someone holding that certificate can use the public key it contains to **establish secure communications with another party**, or validate documents digitally signed by the corresponding private key.
# Certificates
X.509 certificates bind an identity to a public key, using a digital signature.
In the X.509 system, there are **two types of certificates:** *CA Certificates*, and *end-entity certificates*.
## CA Certificates
A CA Certificate can **sign other certificates**. The top level CA certificate is self-signed by the Certificate Authority, and is sometimes called the *Root CA Certificate*.
Other CA certificates are called *intermediate* or *subordinate* CA certificates.
## End-Entity Certificates
An end-entity, on the other hand, identifies **the user**, like a person or a business.
An end-entity certificate **cannot sign other certificates**.
These certificates are sometimes called *leaf* certificates.
## Extensions
- `.pem`
- `.cer`, `.crt`, `.der`
- `.p8`, `p8e`, `pk8`

> [!TODO] Note-taking in progress!
> [X.509 - Wikipedia](https://en.wikipedia.org/wiki/X.509#Certificate_filename_extensions)

# Certificate Chains
A certificate chain is a **list of certificates, usually starting with a leaf, followed by one (or more) CA Certificates**.
Certificate chains are used in order to **check that the public key contained in a certificate (the first in the chain) effectively belong to its subject**, as well as any data contained within.
They work by having each certificate in the chain except the last one **signed by the secret key corresponding to the next certificate in the chain**.
Effectively, each certificate in the chain validates the next one, who then validates the next one, rinse-and-repeat until the last certificate.
This way, if you reach the last certificate (the *trust anchor*), it proves that the target can be trusted.
Note that individual nodes in a chain can be reused in different chains.
This is because **several CA certificates can be generated for the same subject and public key, but be signed by different private keys**, for example from different Certificate Authorities, or different private keys from the same CA.