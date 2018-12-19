---
layout: post
title: Insight into SecOps
subtitle: Purple by default
tags: [Purple Team, Blue Team, Insight]
image: "/img/SOC_Functions.png"
share-img: "/img/SOC_Functions.png"
comments: true
---

Taking a break from our regularly scheduled Microsoft deep dive, I bring you some insight into daily Security Operations. In a world where we're hired to be a traditional blue teamer, if we have the drive, we often have the opportunity end up becoming a purple teamer (Red + Blue!) in addition to our "day job". In order to maximize our effect on the companies that we are hired to secure, most of us end up wearing the full spectrum of information security hats, which is excellent for those of us that actively look for learning opportunities. That being said, it's now also the season where our families, and even some colleagues, ask us "so what's your job like, what do you really do for company 'X'?". Below I've categorized (most of) the daily work I do in an effort to shed some light for those of you looking to start down the Security Analyst / Engineer path at a small to medium sized company.

Below I've shared a screengrab from the SANS Security Leadership Poster regarding the essential functions that a mature SOC program will employ. Usually, a SOC is made up of a team of 5+ people, with at least 1 person with dedicated responsibility per area, but all work as either traditional analysts or engineers. At a small to mid sized company, you can expect to be wearing all the hats on a much smaller team.

<img src="/img/SecOpsDay/SOC_Functions.png">

### Standard Analyst Duties (Blue Team!)
Here we have the bread and butter responsibilities of a Security Analyst; monitoring the SIEM and the EDR environment, triaging alerts, looking for signs of compromise and determining where remediation actions are necessary. In addition to these tools, I also work with our Intrusion Detection Systems (IDS), Intrusion Prevention Systems (IPS), Anti-Virus platforms, Cloud Access Security Broker (CASB) solution, Email Protection / Anti-Phishing Services, and our Vulnerability Management tools. This involves triaging alerts and discovered vulnerabilities from the tools, as well as maintaining stability and upgrades, tuning the rule bases, and creating new rules for them. Lastly in the bread and butter category, we have the daily tickets that need to be responded to, usually telling us that we are the bane of someone's existance and making their job harder, and that we need to fix something.

- SIEM
- IDS
- IPS
- EDR
- AV
- CASB
- Vulnerability Management
- Tickets

### Proactive Security (Red Team!)
Really it's "Red Team - Lite", and revolves around three major points; security awareness testing/training, penetration testing, and cloud identity audits. Penetration testing and auditing I tend to do bi-yearly, and the awareness training and cloud audits I do daily and monthly respectively. Awareness training comes in many forms, from encouring employees to report suspicious emails, to plugging in Rubber Ducky USB's that rickroll people who leave their machines unlocked; I take great enjoyment in this. The cloud audits I have running on a script, spraying for default/common passwords monthly, and auto generating remediation tickets.

- Cloud Identity Audits
- Penetration Testing
- Phishing Assessments
- Security Awareness Checks
- Proactive Risk Assessments


### Incident Response Work
Remediating malware infections and Identity Compromises, conducting investigations for legal, and engaging with employees on threat remediation takes the bulk of this category. Once an infection/compromise is found, IOC's are obtained and used to hunt across the environment for other infections or evidence of lateral movement. IOC's come in many forms, from hashes, to contacted IP Addresses, registry edits, mailbox rule creations, etc.

- Malware/Suspicious Software Analysis
- Malware Remediation
- Malware IOC Generation and hunting
- Identity Compromise Remediation
- General Fire-Fighting


### Threat Hunting
Ingesting the latest bulletins from the FBI and other relevant threat intelligence sources and feeding the data into our systems; most of this happens automatically. I mention this because most analysts think that this is what threat hunting is, when really this is just the start. Threat hunting is asking a question of your environment, and hunting for the answer. For example, are there any encrypted PowerShell commands running in my environment? If so, what are they, and do any look malicious? You go down a rabbit hole trying to answer a specific question. In my opinion, threat hunting is looking for strange behaviors or specific signs of compromise using published IOC's, often in the form of YARA rules or published reports filtered down. Another example that I often see in regards to malware is Winword.exe (Microsoft Word) invoking the command line or PowerShell, that's usually a good item to hunt for in your environment then review.


### Security Engineering
Here we have tool lifecycle management and updates/upgrades. I've also included tweaking their rules, setup and policies under this heading; as sometimes these tasks are delegated to an Engineer role as opposed to an analyst. Included here is also tool deployment (so, so, so many Microsoft tools), revamping, and integration with other tools; i.e cobbling together python scripts to use the malware sandbox API and have it talk to the SIEM. Finally, we have the allmighty task of creating Standard Operating Procedures (SOP's), compliance documentation and random project work!

- Projects, projects, so many projects ("initiatives")

### The Cloud!
Is your corporation moving towards "The Cloud"? Cloud servers, cloud email, cloud storage, cloud pizza parties? Well then, it sounds like it's time to build out a secure network design including security groups, system hardening, and you should probably follow some sort of framework. I recommend either the Risk Management Framework, NIST 800-53, and utilizing ISO-27001 controls / CIS Level 1 benchmarks for system deployment. Also of absolute necessity for anything internet facing that is tied to your Active Directory, is for the security team to weild the all-mighty MFA bat. Multi Factor Authentication. Weild that beast, hit everyone with it. Or at least used risk based logon policies. Without it, all it takes is an adversary to spray your environment with a common password (Winter2018) and boom, initial access to your corporate environment.

<img src="/img/SecOpsDay/YellAtCloud.png">


