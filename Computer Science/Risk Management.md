---
tags:
  - concept
  - security
---
Risk Management is the **process of identifying, assessing, and mitigating risks in an organization's security**. Risk in this case is the potential of a threat acting on a vulnerability.
Threats aren't limited to bad actors, they can also include natural threats like earthquakes, or technical threats such as power outages.
A Risk Management *Policy* is a **set of procedures and processes designed to mitigate risks, and their potential effects on an organization**.
# Methodology
There exist **several frameworks for risk assessment**. Here are a few examples:
- **NIST SP 800-30**: Developed by the [[National Institute of Standard and Technology]].
  It involves identifying and evaluating risks, determining their likelihood and impact, and developing a risk response plan.
- **Facilitated Risk Analysis Process (FRAP)**: This one involves a group of stakeholders working together to identify and evaluate the org's risks.
  It is designed to be more collaborative and inclusive.
- **Operationally Critical Threat, Asset, and Vulnerability Evaluation (OCTAVE)**: Focuses on identifying and prioritizing assets based on their importance in an organization's architecture and mission.
- **Failure Modes and Effect Analysis (FMEA)**: Commonly used in engineering and manufacturing contexts.
  It involves identifying potential failure modes of a system or process, and analyzing the possible effects of those failures, as well as their likelihoods.
# Example Process
Here is an example risk management process.
## 1. Frame Risk
Risk management **begins with establishing the risk context, or "framing" risk**.
Organizations have to define a *risk frame* to prepare the terrain for managing risk. This way, they provide limits to risk-based decision to not go overboard in their zeal to secure their architecture.
To do so, organizations have to identify the following important points:
- **Risk Assumptions**: What do we assume about threats and vulnerabilities? What is their likelihood, and what would be their impact?
- **Risk Constraints**: What are the constraints we're setting on assessing, responding, and monitoring risks?
- **Risk Tolerance**: What kind of risks and level of uncertainty are we ready to accept?
- **Priorities and Trade-offs**: What are the highest priorities in terms of our business functions? What are the trade-offs between the different types of risks faced?
## 2. Assess Risk
The second part of a good risk management strategy, assessing risks **involves examining risks with the organization's risk framework**.
The goals here are to **determine threats, vulnerabilities, impacts of risks and their likelihoods**.
## 3. Analyze Risk
There are **two main approaches to risk analysis**:
- **Qualitative Risk Analysis**, where every risk gets assigned a ranking, like "high, medium, low", or colors.
- **Quantitative Risk Analysis**, where every risk gets assigned a number, like one from 0 to 10.
This step helps the organization prioritize risks based on the ratings or numbers we've given them here.
### Formula Example
#### Single Loss Expectancy
`SLE = AssetValue * EF`
SLE is the **value of your asset multiplied with the exposure factor** (a percentage of loss a realized threat can cause to your asset).
For example, with an asset value of $10'000 (10% laptop, 90% data), and an EF of 90% (the whole data, in this case), you'd get an SLE of $9'000.
#### Annualized Loss Expectancy
`ALE = SLE * ARO`
Then, ALE helps us find the **expected loss per year**, which guides us to decide whether paying to mitigate a vulnerability is justified.
Annualized Rate of Occurence or ARO is the **expected number of times this threat is realized per year**.
For example, with an SLE of $9'000 as per the last example, and an annualized rate of occurence of 0.5 (once every two years), we get an ALE of $4'500.
This means that we get an annualized cost of **4'500 per laptop** unless we take proper measures.
The decision whether to mitigate that or not depends then on the risk tolerance of the organization.
## 4. Respond to Risk
There are multiple ways to respond to a risk once it has been analyzed. They all **depend on the probability of occurrence, the costs of countermeasures, and of course the severity of the threat**.
- **Avoid Risk**: This is about eliminating the risk altogether.
  For example, cutting off internet access from important assets to prevent online threats. Or asking one's employees to work exclusively on the on-premises workstations to prevent data theft.
- **Transfer or Share Risk**: If the risk is too high to handle by an organization on its own, it can decide to purchase insurance ("sharing" risk). For example, fire insurance.
- **Mitigate or Reduce Risk**: Investing in countermeasures helps mitigate risks. For example, to protect against computer viruses, a company might invest in antivirus solutions. This is less extreme than the "Avoid Risk" strategy.
- **Accept Risk**: Sometimes, the cost of mitigating or avoiding a risk is too high compared to the actual loses it would cause, and you must accept it.
  Importantly, accepting a risk does not mean ignoring it. The risk is still analyzed, and a conscious, informed decision was made to let it be for now.
## 5. Monitor Risk
Once a risk has been assessed and a decision has been made, our work isn't done yet.
We now need to **keep monitoring it and all other risks possible**.
This is particularly helpful to **find and add new risks to our management strategy, eliminate risks that are no longer relevant, and assessing our responses to existing risks**.
### Effectiveness Monitoring
This helps define **whether a response to a risk was effective or not**. If the control you put into place isn't effective, or worse, creates new risks, you need to rethink your approach.
### Monitoring Change
This is about **monitoring for change in the threat landscape, which would create new risks**.
This could also be **internal changes**, such as new positions, companies, equipment, that also create new risks.
### Compliance Monitoring
The threat and vulnerability landscape isn't the only thing we need to monitor.
**New laws, industry standards, and regulations can also push us to rethink our risk management approach**.