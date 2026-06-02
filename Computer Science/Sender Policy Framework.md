---
tags:
  - networking
  - email
  - standard
abbreviation: SPF
---
Sender Policy Framework is **an email authentication method** which ensures that **the sending mail server has the permission to send email on behalf of the sender's domain**.
# How It Works
You set up SPF by **publishing a TXT [[Domain Name System]] record on your domain, containing a list of authorized senders**.
When a receiver gets a message, it verifies the *envelope sender*'s IP against the ones mentioned in the SPF TXT record you set up.
## Policies
- `-all`: Fail.
- `~all`: Softfail.
- `?all`: Neutral.
# Limitations
- There is a hard limit of **10 DNS lookups per evaluation**. This can cause problematic for larger organizations.
- SPF alone **doesn't prevent visible email spoofing**, since it only verifies the *envelope sender*, not the `From:` field of the actual email.
- SPF **breaks when mail is forwarded**, because the forwarding server's IP isn't in the original sender's SPF record.