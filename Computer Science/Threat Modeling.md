---
tags:
  - concept
  - security
---
Threat modeling is **a systematic approach to the identification, prioritization, and addressing of potential security threats in an organization**.
All in all, threat modeling **allows an organization to make informed decision on how to harden their security**, by conducting attack scenarios and assessing the current vulnerabilities of its systems.
# Key Terminology
## Threat
**Any potential occurrence, event, or actor that may exploit vulnerabilities to compromise the organization's CIA triad.**
This can take many forms, including cyberattacks, human errors, or natural disasters.
## Vulnerability
**A weakness or flaw in a given system, application, or process that may be exploited to cause harm.**
This includes software bugs, misconfiguration issues, or design flaws, but is much broader than these three things.
## Risk
A risk is **a threat combined with a vulnerability, in effect, a threat finding out and acting on that vulnerability**.
# Process of Threat Modeling
At a high level, a threat modeling process goes a little bit like his:
1. **Define the scope** to identify the systems, applications, and networks that will be targeted.
2. **Identify assets** by developing diagrams and visual representations of the organization's systems, and its dependencies.
   It is also essential in those elements to outline the importance of each system in the overall architecture, as well as based on the information it handles (personal data, financial information, intellectual property).
3. **Identify threats** to know what you're up against, and what to prepare for.
4. **Analyze vulnerabilities and prioritize risks** based on the potential impact of those risks.
   Then, prioritize for the most severe ones.
   Some useful resources for this step include the [[MITRE ATT&CK]] framework.
5. **Develop and implement countermeasures** to mitigate those risks.
   This can range from better access controls, to system updates, as well as regular security assessments.
6. **Monitor and evaluate** your work so that it keeps being efficient and you can find new risks quicker.
# Typical Teams Structure
- **Security Team**: Leads the threat modeling process. Provides expertise on threats, vulnerabilities, and risk mitigation strategies. Ensures that security measures are implemented, validated, and monitored continuously.
- **Development Team**: Builds secure systems and applications. Makes sure security is considered at all stages of the development life cycle.
- **IT and Operations Team**: Manages the organization's infrastructure (networks, servers, critical systems). Provides knowledge of the infrastructure of the organization.
- **Governance, Risk, and Compliance Team**: Responsible for organization-wide compliance assessments based on industry regulations and internal policies. Collaborates with the security team to align on threat modeling regarding the organization's risk management objectives.
- **Business Stakeholders**: Provide input on the organization's priorities and risk tolerance. Ensure that the threat modeling process aligns with these.
- **End Users**: Provide a valuable perspective on the organization's systems and its features. Enables the identification of vulnerabilities and risks specific to user interactions and behaviors.
# Attack Tree
An attack tree is **a visual representation of the ways a malicious actor might go about fulfilling an objective**.
It represents the objective as the top node, and then branches out into **first high-level strategies, and then specific attack vectors fulfilling those strategies**.
Each individual node then further breaks down into smaller steps, so that it's easy to reproduce.
![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5dbea226085ab6182a2ee0f7/room-content/ab10d8571dca42dfcab63c952c436413.png)