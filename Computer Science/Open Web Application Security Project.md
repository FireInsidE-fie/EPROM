---
tags:
  - organization
  - security
abbreviation: OWASP
---
OWASP is a **nonprofit foundation focused on understanding web technologies and exploitation** and providing resources and tools designed to **improve the security of software applications**.
It analyzes how the *IAAA principles* (Identity, Authentication, Authorization, and Accountability) were implemented and how they failed at implementing it.
# OWASP Top 10 (2025)
OWASP categories are built on **causes of vulnerabilities**.
The **ranking isn't data-driven**, as in they do look at data but the number of vulnerabilities is not deterministic.
## A01 - Broken Access Control
When the server doesn't enforce **who can access what**.
### Examples
- [[Insecure Direct Object Reference]]
## A02 - Security Misconfiguration
Security Misconfigurations happen on systems that have been **deployed with generally bad configuration**.
These aren't bugs in the logic of the code or anything, just badly set up systems and services that leave gaping flaws in their **semantic logic**.
### Examples
- **Default credentials or weak passwords** left unchanged
- **Unnecessary** services or endpoints exposed to the internet
- Misconfigured cloud storage or permissions (S3, Azure Blob, GCP buckets)
- **Unrestricted** API access or missing authentication/authorization
- **Verbose error messages** exposing stacktraces or system details
- **Outdated** software, frameworks, or containers with known vulnerabilities
- **Exposed AI/ML endpoints** without proper access controls
## A03 - Software Supply Chain Failures
Supply Chain Failures occur **when a software's dependencies are compromised or just plain outdated**.
This causes the software to become vulnerable by (probably) no fault of its own.
### Examples
- Using **unverified or unmaintained** libraries and dependencies
- **Automatically** installing **updates** without verification
- Overreliance on **third-party AI models** without monitoring or auditing
- Insecure **build pipelines or CI/CD** processes that allow tampering
- Poor **license** or provenance **tracking** for components
- Lack of **monitoring** for vulnerabilities in dependencies after deployment
## A04 - Cryptographic Failures
Cryptographic failures **happen when sensitive data isn't encrypted, or is badly encrypted**.
This can include storing passwords in plaintext, using outdated or weak algorithms, or not securing data that's sent over the wire.
Usually, **you shouldn't roll your own cryptographic system**. Instead, use well-established libraries that will do the job better, and more reliably.
## A05 - Injection
Injection happens when **user input isn't sanitized and mishandles it**.
Instead of processing the data like it should be, it passes it to a piece of software that can execute commands.
This leads to input being able to execute commands on the host running the software.
### Examples
- [[SQL Injection]]
- [[Command Injection]]
- AI Prompts
- [[Server Side Template Injection]]
## A06 - Insecure Design
## A07 - Authentication Failures
When an application **can't reliably verify the identity of its user**.
### Examples
- Username Enumeration
- Weak/guessable Passwords
- Logic flaws in the login/registration flow
- Insecure session or cookie handling
## A08 - Software or Data Integrity Failures
These occur **when an application relies on code, data, or updates without verifying them first**.
This mainly happens by not verifying the integrity of the data you're using when it comes from outside sources.
## A09 - Security Logging & Alerting Failures
This occurs when **defenders can't detect or investigate attacks**.
## A10 - Mishandling of Exceptional Conditions
# OWASP Top 10 (2021)
## 1. Broken Access Control
Accessing web pages standard users aren't supposed to access is still the most widely found vulnerabilities on web applications.
Simply put, **you bypass authorization** to access resources you aren't supposed to.
### Examples
[[Insecure Direct Object Reference]]
## 2. Cryptographic Failures
A misuse or lack of use of cryptographic algorithms for protecting sensitive information.
Those failures can occur both at rest (on disk) and on the wire.
### Examples
[[Man in The Middle Attack]]
## 3. Injection
Injections occur when an application interprets user input as commands or parameters, allowing for unwanted code execution based on user input.
### Examples
[[SQL Injection]]
[[Command Injection]]
## 4. Insecure Design
These are vulnerabilities **inherent to the application's architecture**. The design itself, not the implementation, is flawed in its logic.
These can range from shortcuts in security left behind from testing stages, to just not thinking of all possible cases.
For example, in the case of a password reset 6-digit code sent by SMS, you could try to mitigate brute-forcing by rate-limiting [[IP Address]]es, but what if multiple addresses try to crack the same code and you haven't put securities in place for multiple hosts targeting the same code?
These are tough to fix once introduced, as they often result of oversight on the part of the designers, most often before the code was even written.
The best approach is to **perform threat modelling early on in the design lifecycle**.
## 5. Security Misconfiguration
These occur when **security could have properly configured, but was not**.
These can be very varied, but examples include keeping debugging interfaces up, not enabling some crucial security features, default passwords or default accounts, and many, many more.
## 6. Vulnerable and Outdated Components
## 7. Identification and Authentication Failures
These are a range of **failures related to authentication** and making sure a user has the needed rights to access a resource.
You can mitigate those weaknesses by ensuring strong password policies to evade brute forcing, rate-limiting access to resources and log-on attempts, as well as implementing multi-factor authentication.
### Examples
- Brute force attacks
- Use of weak credentials
- Weak Session Cookies
## 8. Software and Data Integrity Failures
Integrity means **being certain that a piece of data wasn't tampered with**. It is essential to maintain important data free from unwanted or malicious modifications.
You ensure integrity in part using [[Hash]]es.