---
tags:
  - security
  - framework
---
The STRIDE is a **thread modeling framework methodology developed by [[Microsoft]]**.
Its goal is to **help identify and categorize potential security threats in software development and system design**.
# Acronym
As with the [[DREAD Framework]], the STRIDE Framework is an acronym of the following threat categories, all violating a specific CIA triad part.
## Spoofing
Unauthorized access or impersonation of a user or system.
Violates Authentication.
### Examples
- Sending an email as another user.
- Creating a phishing website to harvest user credentials.
## Tampering
Unauthorized modification or manipulation of data or code.
Violates Integrity.
### Examples
- Changing the password of another user.
- Installing back doors in a system.
## Repudiation
Ability to deny having acted, usually due to insufficient auditing or logging.
Violates Non-repudiation.
### Examples
- Being able to deny that an unauthorized money transaction occurred.
- Being able to deny that an offensive message was sent to another person.
## Information Disclosure
Unauthorized access to sensitive information, like personal or financial data.
Violates Confidentiality.
### Examples
- Unauthorized access to a database with personal information of users.
- Accessing public cloud storage that handles sensitive documents.
## Denial of Service
Disruption of the system's availability, preventing legitimate users from accessing it.
Violates Availability.
### Examples
- Overwhelming a web server with too many requests, preventing access.
- Deploying a ransomware that encrypts data and prevents access.
## Elevation of Privilege
Unauthorized elevation of access privileges, which allows threat actors to perform unintended actions.
Violates Authorization.
### Examples
- Creating a regular user but still being able to access superuser stuff.
- Gaining admin access by abusing an unpatched system.
# STRIDE for Threat Modeling
You can use the STRIDE Framework for [[Threat Modeling]], where you can integrate it by using a process that **identifies, assesses, and mitigates security risks**.
Here's an example of such a process:
1. System Decomposition into components (apps, networks, data flows)
2. Applying STRIDE categories for each component
3. Threat Assessment
4. Developing countermeasures
5. Validating and verifying findings
6. Continuous Improvement