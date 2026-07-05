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

**- New Write‑Up Coming Soon (block unauthorised SSH login - Junior Security Analyst Intro task)**

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
