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
