---
tags:
  - networking
  - protocol
  - email
---
Domain-based Message Authentication, Reporting and Conformance or DMARC (phew) is **an email authentication protocol**.
It is designed to prevent *email spoofing* by extending both [[Sender Policy Framework]] and [[DomainKeys Identified Mail]].
# How It Works
Similarly to SPF and DKIM, **DMARC uses the [[Domain Name System]] to help recipients of emails verify their legitimacy**.
You put a TXT record with name format `_dmarc.<domain>`, which specifies a few options and, most crucially, *alignment*.
Alignment allows you to **determine whether a domain is close enough to your own domain to be considered "aligned"**.
Alignment can be either *strict* (exact match of the domain) or *relaxed* (same parent domain).
You also define the policy tag in the `p=` option of the TXT record. This defines what to do with messages that fail DMARC's verification, and can be several different values:
- `none`: Do nothing, just report
- `quarantine`: Spam folder
- `reject`: Bounce at [[Simple Mail Transfer Protocol]]
The **recipients** of emails claiming to be `From:` your domain can then **check your DMARC DNS record**, and know **what to do with the ones that don't match** (according to the policy you yourself defined).
They do this by literally just using the domain from the `From:` header, and querying `_dmarc.yourdomain.com`.