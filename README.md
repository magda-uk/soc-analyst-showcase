[![Magda Dominguez Portfolio](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=23&pause=1000&color=00AEEF&vCenter=true&width=680&height=40&lines=Magda+Dominguez+%7C+Cybersecurity%2C+SOC+%26+AppSec)](https://www.linkedin.com/in/magda-d-infosec)

[![Microsoft Sentinel](https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)]()
[![Wazuh SIEM](https://img.shields.io/badge/Wazuh-00AEEF?style=for-the-badge&logo=wazuh&logoColor=white)]()
[![Sysmon](https://img.shields.io/badge/Sysmon_Telemetry-4B0082?style=for-the-badge&logo=windows&logoColor=white)]()
[![KQL](https://img.shields.io/badge/KQL_Hunting-00509E?style=for-the-badge&logo=azuredataexplorer&logoColor=white)]()
[![Microsoft Entra ID](https://img.shields.io/badge/Entra_ID-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)]()
[![OWASP AppSec](https://img.shields.io/badge/OWASP_AppSec-000000?style=for-the-badge&logo=owasp&logoColor=white)]()
[![Python Security](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)]()

**Target Role:** Cyber Security Analyst | SOC / Blue Team | Security Design & AppSec  
**Certifications:** BCS CISMP | Microsoft SC-900  
**Location:** Bristol, UK (Hybrid / Remote)

---

## 🔺 Executive Summary & Analytical Mindset

This repository is a curated showcase of my highest-fidelity threat triage cases, detection engineering projects, and enterprise lab architecture. 

My analytical approach is rooted in my professional background in Perpetual Inventory within high-volume inbound logistics. Managing continuous stock reconciliation and investigating critical supply chain discrepancies requires a meticulous, evidence-based mindset. I apply this exact methodology to cybersecurity: **tracing anomalous behaviour across multiple systems, separating noise from true positive alerts, and reconstructing attack timelines from raw telemetry.**

*(Note: For a complete view of my daily hands-on labs, foundational training, and operational playbooks, please visit my **[Continuous Learning Repository](https://github.com/magda-uk/soc-analyst-portfolio/tree/main)**.)*

---
## 🔺 Advanced Threat Hunting & Triage Highlights

The following investigations represent my strongest end-to-end analytical work. They demonstrate my ability to ingest raw logs, map behaviour across all 14 MITRE ATT&CK tactics, and formulate actionable incident response recommendations. 

*(All links below direct to my dedicated **[MITRE ATT&CK & Threat Hunting Repository](https://github.com/magda-uk/mitre-attack-mapping)**).*

### 1. End-to-End Threat Hunt: Procdump Credential Extraction & SOAR Automation
- **Tactics & Techniques:** TA0006 Credential Access (T1003), TA0010 Exfiltration (T1048).
- **Technologies:** Sysmon (ID 1, 3, 11), KQL, Microsoft Sentinel, Azure Logic Apps (SOAR).
- **Why it matters:** Demonstrates the full SOC lifecycle. I reconstructed a multi-stage attack bypassing LSASS protections to dump `explorer.exe` memory. I then engineered a custom KQL query to correlate the execution with PowerShell outbound exfiltration, and built a Sentinel SOAR playbook to automate the L1 analyst alert triage.
- 🔗 **[View Full Playbook & SOAR Automation](https://github.com/magda-uk/mitre-attack-mapping/blob/main/01-MITRE-ATTACK-Investigations/TA0010-Exfiltration/README.md)**

### 2. False Positive Triage: IPv6 DNS Resolution & Electron Architecture
- **Tactics & Techniques:** TA0011 Command and Control (T1071.004).
- **Technologies:** Sysmon (ID 3), IPv6 Subnetting, UDP Network Traffic.
- **Why it matters:** Showcases deep technical maturity. Instead of blindly alerting on outbound UDP port 53 traffic, I mathematically validated the `/64` IPv6 subnet prefix to prove the destination was a benign local resolver, correlating the behaviour with VS Code's asynchronous Node.js network stack to prevent SIEM alert fatigue.
- 🔗 **[View False Positive Analysis](https://github.com/magda-uk/mitre-attack-mapping/blob/main/01-MITRE-ATTACK-Investigations/TA0011-Command-and-Control/False-Positive-DNS-IPv6/README.md)**

### 3. Incident Investigation: LSASS Memory Access via Mimikatz
- **Tactics & Techniques:** TA0006 Credential Access (T1003.001).
- **Technologies:** Sysmon (ID 10), Windows API, Digital Forensics.
- **Why it matters:** Highlights OS-level forensic analysis. By dissecting a Sysmon Event ID 10 alert, I identified the specific `0x1010` hexadecimal code, translating it to `PROCESS_VM_READ` and `PROCESS_QUERY_LIMITED_INFORMATION`, definitively proving the untrusted process requested the exact permissions required to dump credentials from memory.
- 🔗 **[View LSASS Memory Triage](https://github.com/magda-uk/mitre-attack-mapping/blob/main/01-MITRE-ATTACK-Investigations/TA0006-Credential-Access/Mimikatz-LSASS-Access/README.md)**

### 4. Cloud Identity: Impossible Travel & Authentication Anomalies
- **Tactics & Techniques:** TA0001 Initial Access / TA0003 Persistence (T1078).
- **Technologies:** Microsoft Entra ID, Sentinel, KQL.
- **Why it matters:** Demonstrates proactive cloud threat hunting. I utilized KQL data binning to baseline Entra ID sign-in telemetry, identifying MFA bypass attempts, brute-force spikes, and geo-velocity anomalies indicative of account compromise.
- 🔗 **[View KQL Authentication Playbook](https://github.com/magda-uk/mitre-attack-mapping/blob/main/02-Threat-Hunting-Playbooks/authentication-anomalies/README.md)**

### 5. Email Threat Triage: Brand Impersonation & Bayesian Poisoning
- **Tactics & Techniques:** TA0001 Initial Access (T1566.002), TA0005 Stealth (T1027).
- **Technologies:** Email Header Analysis, Spam Filter Evasion, Phishing Triage.
- **Why it matters:** Phishing triage goes beyond just checking URLs on VirusTotal. In this investigation of a targeted "Mercadona" brand impersonation campaign, I uncovered the use of **Bayesian Poisoning**. The attacker embedded invisible, legitimate text block quotes within the HTML to manipulate and bypass machine-learning spam filters. This highlights my ability to dissect advanced evasion techniques and understand how defensive mechanisms are actively subverted by threat actors.
- 🔗 **[View Phishing & Evasion Analysis](https://github.com/magda-uk/mitre-attack-mapping/blob/main/01-MITRE-ATTACK-Investigations/TA0001-Initial-Access/Phishing-Mercadona-Evasion/README.md)**





---

## 🔺 Enterprise Telemetry & Adversary Emulation

My investigations rely on a hybrid telemetry architecture. While many of my deep-dive forensic analyses are conducted directly on the endpoint (parsing raw Sysmon and Windows Event Logs), I also engineered a distributed SIEM environment to emulate and detect complex attack lifecycles.

### 1. Ransomware Emulation & FIM (Supply Chain Impact)
- **Objective:** Simulate a localized ransomware infection targeting critical logistics data (Perpetual Inventory & Good Faith Receiving) and detect the encryption process in real-time.
- **Infrastructure:** Wazuh SIEM (Ubuntu), File Integrity Monitoring (Syscheck), Python.
- **Why it matters:** Connects cyber threats to real-world business operations. Drawing from my background in logistics, I simulated a targeted attack on Perpetual Inventory data. I configured Wazuh FIM to detect mass file modifications (T1486) in real-time, highlighting the critical need for rapid SOC triage to prevent supply chain disruption.
- 🔗 **[View Ransomware & FIM Analysis](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/5.projects/wazuh-ransomware-fim/README.md)**

### 2. Distributed SIEM & Endpoint Visibility
- **Endpoint Configuration:** Windows 10/11 VMs tuned with Sysmon (SwiftOnSecurity baseline) and advanced Audit Policies to capture high-fidelity forensic data (Process Creation, Network Connections, ScriptBlock Logging).
- **SIEM Infrastructure:** Wazuh Server deployed to aggregate endpoint telemetry, simulate adversarial campaigns (NLA evasion, persistence), and validate custom detection rules.
- 🔗 **[View SIEM Lab Architecture](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/5.projects/wazuh-lab/README.md)**

---

## 🔺 Detection Engineering & Active Defence

Moving beyond reactive analysis, I develop custom rules and proactive defence mechanisms (mapped to MITRE D3FEND) to identify specific adversarial behaviours before impact occurs.

- 🍯 **[Active Defence: Honeytokens & Cyber Deception (D3-DO)](https://github.com/magda-uk/mitre-attack-mapping/blob/main/02-Threat-Hunting-Playbooks/active-defence-honeytokens/README.md)**
- 📄 **[Sigma Rule: Malicious Registry Modification for Persistence](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/1.detections/3.rules/sigma/registry-modification-persistence-tracking.yml)**
- 📄 **[KQL Query: Suspicious PowerShell Encoded Command Execution](https://github.com/magda-uk/mitre-attack-mapping/blob/main/02-Threat-Hunting-Playbooks/powershell-encoded/README.md)**

---

## 🔺 Phishing Incident Response & Artefact Triage
A dedicated laboratory environment focused on the end-to-end triage of phishing campaigns and the safe handling of malicious attachments. 

This project demonstrates core Blue Team capabilities in email routing analysis (SPF/DKIM/DMARC) and the static analysis of malicious PDF artefacts (T1566) to extract Indicators of Compromise (IoCs).

- 🔗  **[Explore the Phishing Incident Response Lab](https://github.com/magda-uk/phishing-incident-response-lab/blob/main/README.md)**

---

## 🔺 Application Security, Threat Modelling & Secure Design

Beyond SIEM alert triage, I leverage my Software & Data Engineering background to perform architectural threat modelling, API penetration testing, and code-level remediation.

### Shelfie REST API: Security Audit, STRIDE Threat Model & Remediation
- **Objective:** Conduct an end-to-end security assessment of a four-layer Python (Flask) and MySQL REST API, mapping architectural flaws to **STRIDE**, **OWASP API Security Top 10**, and **MITRE ATT&CK**.
- **Key Findings & Exploitation:** Validated Broken Object Level Authorisation / IDOR (`CWE-639`), Stored XSS (`CWE-79`), Authentication Brute-Force (`CWE-307`), and Werkzeug Debugger PIN exposure (`CWE-200`) using **Burp Suite** and **OWASP ZAP**.
- **Engineering & Defense-in-Depth:** Authored a Low-Level Design (LLD) Remediation Playbook implementing contextual JWT decorators (`@token_required`), `Flask-Limiter` rate throttling, `Pydantic` + `NFKC` input validation, `Flask-Talisman` (HTTPS/HSTS), and MySQL Principle of Least Privilege (`DML-only` permissions).
- 🔗 **[Explore the Security Audit & Threat Model Repo](https://github.com/magda-uk/shelfie-security-audit)** | 🛠️ **[View Technical Remediation Playbook](https://github.com/magda-uk/shelfie-security-audit/blob/main/docs/remediation-playbook.md)**

---
## 🔺 Connect with me
[![Magda Dominguez LinkedIn](https://img.shields.io/badge/Magda_Dominguez-Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=000000)](https://www.linkedin.com/in/magda-d-infosec)

I am actively seeking a Cyber Security / SOC / Security Design role where I can bring my structured troubleshooting, log analysis, and secure architecture skills to a dedicated security team.
