# SOC SIEM Dashboard Simulator – Phishing Alert Handling

## Overview
This write-up documents my experience using the TryHackMe SOC SIEM dashboard simulator to investigate, triage, and respond to phishing alerts. I analysed email logs, correlated events across multiple data sources, and made decisions based on real indicators of compromise.

## Investigation Workflow

### 1. Reviewing the Initial Alert
- Checked sender domain and IP address using threat intelligent and detection software to verify if known malicious reputation
- Inspected subject line, for URL shorteners, and spoofed domains 
- Looked for key details like the 5W's (Who, What, When, Where, and Why}

### 2. Correlating SIEM Logs (Splunk)
- Used Splunk to query email logs for similar events
- Checked proxy logs and firewall logs on Splunk for link clicks

### 3. Identifying Phishing Indicators
- Newly registered or suspicious domains by using threat intelligently feeds
- Suspicious links/URLs
- Dangerous attachment types (.zip, .docm)
- Spoofed domains, urgent requests, request for credential change

### 4. Triage & Response
- Marked true positives when user interaction + malicious indicators were present
- Recommended account lockout, credential reset, IP blocking, blocking sender domain and user education
- Documented false positives with reasoning and suggested rule tuning

## Key Learnings
- Correlating SIEM logs, dashboard alerts, and business context to gaining deeper insights into security events and understanding the full picture behind each alert.
- Use of threat intel feeds/tools and SIEM tools (Splunk)
- Making evidence-based triage decisions
- Utilizing company playbooks for remediation, incident response and escalation where required 
- Reducing SOC noise by identifying false positives
- Writing clear investigation notes for handoff and escalation where required
