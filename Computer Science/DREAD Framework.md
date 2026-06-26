---
tags:
  - security
  - framework
---
The DREAD framework is a **risk assessment model developed by [[Microsoft]] to evaluate and prioritize threats and vulnerabilities**.
 It is **opinionated, and relies heavily on the analyst's interpretation and assessment**.
# Acronym
DREAD is an acronym that stands for the following elements.
## Damage
> How bad would an attack be?

The potential harm that could **result from the successful exploitation of a vulnerability.**
This can include data loss, system downtime, or reputation harm.
## Reproducibility
> How easy it is to reproduce the attack?

The ease with which an attacker can **successfully recreate the exploitation of a vulnerability**.
An exploitation being more reproducible probably means the vulnerability is too straight-forward, posing greater screen.
## Exploitability
> How much work is it to launch the attack?

The **difficulty of exploiting a vulnerability**, considering technical skills, tools, or exploits for this vulnerability, and time taken to exploit it successfully.
## Affected Users
> How many people will be impacted?

The number or percentage of users potentially affected by an exploited vulnerability.
## Discoverability
> How easy is it to discover the vulnerability?

The ease with which an attacker can find and identify the vulnerability.
# Guidelines
Since DREAD is pretty opinionated, it can be pretty subjective.
However, there are certain guidelines you can impose to make it more efficient:
- Establish a set of guidelines and definitions **for each DREAD category that explains how to rate vulnerabilities**. This way, you keep a consistent rating scheme.
  This is best used in conjunction with concrete examples of how to rate vulnerabilities.
- Encourage collaboration and get opinions of multiple people and experts.
  Get constructive feedback on ratings.
- Don't use the DREAD framework in a vacuum; use it in tandem with other risk-assessment methodologies.
  Regularly review and update the chosen methods to keep accurate and relevant ratings.