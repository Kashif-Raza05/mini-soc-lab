# Mini SOC Lab with Wazuh SIEM

A small home lab where I simulate basic attacks against my own virtual machines, detect them in a SIEM, and write incident reports like a Tier 1 SOC analyst.

## Objective
Practice the SOC workflow end to end: collect logs, detect suspicious activity, triage alerts, map them to MITRE ATT&CK, and document findings.

> All testing was done only on my own isolated lab machines.

## Lab architecture

![Lab diagram](diagrams/lab-architecture.png)

| Machine | OS | Role | IP |
|---|---|---|---|
| Wazuh Server | [Ubuntu Server version] | SIEM manager and dashboard | [192.168.x.x] |
| Victim | [Ubuntu / Windows version] | Monitored endpoint (Wazuh agent) | [192.168.x.x] |
| Attacker | Kali Linux | Generates test activity | [192.168.x.x] |

Network: [VirtualBox host-only network, no internet access to the victim]

## Tools used
- VirtualBox [version]
- Wazuh [version]
- Kali Linux, Nmap [add Hydra, etc. only if you used them]

## Setup steps
1. Created three VMs with [RAM / CPU / disk settings]
2. Installed Wazuh server and dashboard
3. Installed and registered the Wazuh agent on the victim machine
4. Confirmed the agent shows as **Active** in the dashboard

Screenshots: `screenshots/setup/`

## Simulated activity and detections

| # | Activity (from Kali) | Wazuh alert seen | MITRE ATT&CK | Severity |
|---|---|---|---|---|
| 1 | Nmap port scan of victim | [alert name / rule ID] | T1046 - Network Service Discovery | [Low/Med/High] |
| 2 | Repeated failed SSH logins | [alert name / rule ID] | T1110 - Brute Force | [ ] |
| 3 | [your own test, e.g., new user created] | [ ] | [ ] | [ ] |

## Incident report 1: [Title, e.g., SSH Brute-Force Attempt]

- **Date/time:** [ ]
- **Detected by:** Wazuh rule [ID]
- **Summary:** [2-3 sentences on what happened]
- **Evidence:** [log lines or screenshot filename]
- **Source IP / affected host:** [ ] / [ ]
- **Severity and why:** [ ]
- **MITRE ATT&CK:** [technique]
- **Recommended actions:** [e.g., block the IP, disable password login, enable key-based auth, add fail2ban]

## Incident report 2: [Title]
[Copy the same structure as above]

## Incident report 3: [Title, optional]
[Copy the same structure as above]

## What I learned
- [Honest points: how alerts are generated, difference between noise and real incidents, how severity is decided]
- [Problems you hit and how you fixed them, e.g., agent not connecting]

## Next steps
- [e.g., add a Windows victim, write a custom Wazuh rule, test file integrity monitoring]

## Author
Kashif Raza | [https://www.linkedin.com/in/kashif-raza-9091a222a/] | [kashifraza31703@gmail.com]
