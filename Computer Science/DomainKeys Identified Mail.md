---
tags:
  - networking
  - email
abbreviation: DKIM
---
DomainKeys Identified Mail is **an email authentication method** and Internet standard that **allows a person or organization owning the *signing domain* to associate their domain with an email message**.
DKIM has a big advantage over [[Sender Policy Framework]]: it doesn't break on forwarding, since the signature is attached to the email.
# How It Works
You start by **publishing your DKIM public key in your [[Domain Name System]] with a TXT record**.
This record has to follow the structure `<selector>._domainkey.<domain>`. The selector is useful to rotate keys or have multiple ones.
Then, you configure your mail server so that whenever it sends out a message, **it affixes a signature linked to your [[Domain Name]]**.
This signature is computed with your private key and parts of the email message itself.
Any client receiving the email message will then be able to **query the public key in your DNS to verify that the email is genuine**.