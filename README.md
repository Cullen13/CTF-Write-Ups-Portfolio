# CTF-Write-Ups-Portfolio
A collection of Capture the Flag (CTF) write‑ups documenting my hands‑on cybersecurity learning journey. This repository showcases my methodology, technical skills, and problem‑solving approach across platforms like TryHackMe, HackTheBox, and PicoCTF.

---

## About This Repository
This repo contains detailed, step‑by‑step CTF write‑ups that demonstrate:

- Enumeration and recon techniques  
- Vulnerability identification  
- Exploitation paths  
- Privilege escalation  
- Lessons learned  
- Clear documentation and screenshots  

Each write‑up is structured to reflect real‑world penetration testing methodology.

---

## Repository Structure

ctf-writeups/
│
├── TryHackMe/
│   ├── SOC Level 1: Attack Detection & Containment/
│   │   ├── writeup.md
│   │   └── screenshots/
│   ├── Block unauthorised SSH login/
│   │   ├── writeup.md
│   │   └── screenshots/
│
├── HackTheBox/
│   ├── machine-name/
│   │   ├── writeup.md
│   │   └── screenshots/
│
└── PicoCTF/
├── challenge-name/
│   ├── writeup.md
│   └── screenshots/
---

## Featured Write‑Ups
These are my most complete and polished write‑ups:

**- SOC Level 1: Attack Detection & Containment**

***Overview***

This defensive security challenge simulated a real SOC (Security Operations Center) workflow.
Objectives included:

Detecting suspicious activity

Identifying the attack type

Analyzing threat intelligence

Containing the attacker using firewall rules and rate‑limiting

This exercise demonstrated core SOC analyst skills used in real environments.



***Task 1 — Detect Suspicious Activity***

The monitoring dashboard displayed several alerts indicating abnormal behavior.

Alerts Observed

Web Discovery Attack  
Source IP: 32.122.195.63

Suspicious Port Scanning  
Source IP: 203.0.113.5

Unusual Database Query Pattern  
Source: Internal-DB-01

SQL Injection Attack  
Source IP: 198.51.100.45

Finding

The suspicious IP generating the discovery attempts was:

Code

32.122.195.63



***Task 2 — Identify the Attack Type***

Reviewing the URL Discovery Attempts revealed multiple probes for sensitive endpoints.

Evidence

Code

/admin          → 404

/administrator  → 403

/wp-admin       → 404

/login          → 404

/               → 200

Conclusion

The attacker was performing directory enumeration, attempting to locate hidden or admin pages.



***Task 3 — Threat Intelligence Review***

Threat intelligence confirmed the attacker had a history of malicious activity.

Threat Intel Findings

IP Reputation: Malicious

Geolocation: Moscow, Russia

Previous Attacks: 47

ASN: AS12345

Recommended Actions

Block the source IP

Review admin panel access logs

Apply rate limiting

Update WAF rules



***Task 4 — Contain the Attack***

Containment was performed using the firewall manager.

Firewall Actions Taken

Entered Source IP: 32.122.195.63

Selected Action: BLOCK

Applied the rule

System Confirmation

Code

32.122.195.63 is now blocked. All connection attempts will be dropped.

Additional Security Measure

I also applied rate limiting on the admin ports to slow down rapid automated requests and reduce the impact of enumeration attempts.

Live Log Evidence

All ICMP and TCP attempts from 32.122.195.63 were marked:

Code

BLOCK

Outcome

The attacker was successfully contained and prevented from further probing.



***Final Summary***

This challenge demonstrated key SOC skills:

Alert triage

Log analysis

Attack identification

Threat intelligence interpretation

Firewall rule creation

Rate‑limiting implementation

Incident containment

I identified a malicious IP performing directory enumeration, validated the threat, blocked the attacker, and applied rate limiting for additional protection. This exercise reinforced the importance of layered defense and rapid response in SOC operations.  

**- Block unauthorised SSH login**

**Overview**
This task simulated a Business‑As‑Usual (BAU) investigation performed by a SOC analyst.
I was presented with a SIEM dashboard containing multiple alerts of varying priority and criticality. Two critical alerts stood out:

A successful unauthorized SSH login

Multiple previous failed login attempts on port 22 from the same IP address

Together, these indicated a potentially serious security issue such as:

Credential compromise

Successful enumeration

Attacker pivoting

Because SSH access provides full remote shell control, this event required immediate investigation and containment.

Objectives

Identify the unauthorized user / source IP

Escalate the incident to the relevant team

Contain the threat by blocking the malicious IP and preventing lateral movement

Core Skills Demonstrated

SIEM alert triage

Threat intelligence lookup

Firewall rule modification

Incident escalation and communication

Correlating related alerts to understand attacker behaviour

**Task 1 - Identify the Suspicious IP Address**

I reviewed the SIEM dashboard and confirmed the source IP responsible for:

Failed SSH login attempts

A later successful SSH login

This IP was flagged as the primary threat actor.

**Task 2 - Threat Intelligence Check**

I entered the IP address into a malicious IP reputation checker, which confirmed:

The IP belonged to a known threat actor

It had a history of malicious activity

This validated the severity of the incident.

**Task 3 - Escalation**

I escalated the incident to the relevant internal team for further investigation and tracking, following standard business protocols.

**Task 4 - Containment — Firewall Rule Update**

To stop the attacker from moving laterally or causing further damage, I:

Added the malicious IP to the firewall block list

Confirmed the rule was applied successfully

Ensured all future connection attempts would be dropped


**Final Summary**

How to interpret SIEM alerts and identify critical events

How to correlate related alerts (failed logins → successful login → threat intel)

How to use threat intelligence tools to verify malicious IPs

How to block attackers using firewall rules

How to follow SOC escalation protocols

How to understand the bigger picture of an attacker’s behaviour inside a system

**Screenshots**

<img width="1007" height="1175" alt="image" src="https://github.com/user-attachments/assets/a25ee264-e5c1-4f56-8df8-290bcc89abd5" />

<img width="983" height="1265" alt="image" src="https://github.com/user-attachments/assets/3bad57a4-1aed-430c-8cb6-9e0b3d1d3c70" />

<img width="989" height="1093" alt="image" src="https://github.com/user-attachments/assets/452dcdf8-3750-4168-84bf-f82597d134ca" />






**New Write up  - Coming soon**

I update this repository regularly as I complete more challenges.

---

## Skills Demonstrated
- Enumeration (nmap, gobuster, wpscan)  
- Web exploitation (SQLi, LFI/RFI, weak credentials)  
- Password attacks (hydra, wordlists)  
- Privilege escalation (Linux/Windows techniques, cron jobs, SUID, misconfigurations)  
- Report writing & documentation  
- Scripting & automation (bash, Python — when applicable)

---

## Tools I Use
- nmap  
- gobuster  
- Burp Suite  
- hydra  
- linpeas / winpeas  
- metasploit  
- Python & Bash scripts  

---

## Write‑Up Format
Every write‑up follows a consistent structure:

1. Overview  
2. Recon & Enumeration  
3. Exploitation  
4. Privilege Escalation  
5. Flags  
6. Lessons Learned  

This format mirrors real penetration testing reports and makes my work easy to review.

---

## Why This Repository Exists
This repo serves as:

- A record of my cybersecurity learning journey  
- A showcase of my hands‑on skills for employers  
- A way to practice documentation and reporting  
- A reference for future challenges  

---

## Connect With Me
If you’d like to discuss cybersecurity, collaborate, or provide feedback, feel free to reach out.
