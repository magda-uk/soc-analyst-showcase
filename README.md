# 🛡️ Magda Dominguez | Blue Team & SOC Analyst Portfolio (Showcase)

[![Microsoft Sentinel](https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)]()
[![Wazuh SIEM](https://img.shields.io/badge/Wazuh-00AEEF?style=for-the-badge&logo=wazuh&logoColor=white)]()
[![Sysmon](https://img.shields.io/badge/Sysmon_Telemetry-4B0082?style=for-the-badge&logo=windows&logoColor=white)]()
[![KQL](https://img.shields.io/badge/KQL_Hunting-00509E?style=for-the-badge&logo=azuredataexplorer&logoColor=white)]()
[![Microsoft Entra ID](https://img.shields.io/badge/Entra_ID-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)]()

*Target Role:* SOC Analyst (L1) / Junior Blue Team Analyst  
*Location:* Bristol, UK

---

## 🔺 Executive Summary & Analytical Mindset

This repository is a curated showcase of my highest-fidelity threat triage cases, detection engineering projects, and enterprise lab architecture. 

My analytical approach is rooted in my professional background in Perpetual Inventory within high-volume inbound logistics. Managing continuous stock reconciliation and investigating critical supply chain discrepancies requires a meticulous, evidence-based mindset. I apply this exact methodology to cybersecurity: **tracing anomalous behaviour across multiple systems, separating noise from true positive alerts, and reconstructing attack timelines from raw telemetry.**

*(Note: For a complete view of my daily hands-on labs, foundational training, and operational playbooks, please visit my [Continuous Learning Repository](https://github.com/magda-uk/soc-analyst-portfolio/tree/main).)*

---

## 🔺 Enterprise SOC Architecture (Home Lab)

Before analysing alerts, I built the infrastructure to generate them. I maintain a distributed SIEM environment to simulate attacks, capture host-level telemetry, and validate custom detection rules.

* **SIEM / Manager:** Wazuh Server (Ubuntu Linux)
* **Victim Endpoint:** Windows 10/11 VM + Sysmon (SwiftOnSecurity baseline) + Wazuh Agent
* **Adversary / Red Team:** Kali Linux VM
* **Capabilities Implemented:** EDR telemetry simulation, malicious PowerShell execution monitoring, network scanning detection, and NLA evasion.
* 🔗 **[View Lab Architecture & Setup](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/5.projects/wazuh-lab/README.md)**

---

## 🔺 Featured Investigations (Threat Triage)

The following write-ups demonstrate my ability to ingest raw logs, map behaviour to the MITRE ATT&CK framework, and formulate actionable incident response recommendations.

### 1. Enterprise Lab: RDP Brute Force, NLA Evasion & Persistence
* **Objective:** Simulate an initial access and persistence campaign, evading Network Level Authentication (NLA) and creating a hidden administrative account.
* **Techniques:** T1110.001 (Password Guessing), T1136.001 (Local Account).
* **Skills Applied:** Wazuh SIEM alert triage, chronological log correlation (Event IDs 4625, 4720, 4732), network scanning (Nmap/Ncrack).
* 🔗 **[View RDP Evasion Analysis](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/5.projects/wazuh-lab/t1110-rdp-bruteforce.md)** | 🔗 **[View Persistence Analysis](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/5.projects/wazuh-lab/t1136-persistence-lab.md)**

### 2. Cloud Identity: Impossible Travel & MFA Anomalies
* **Objective:** Triage Entra ID Sign-in logs to identify credential compromise and geolocation (geo-velocity) anomalies.
* **Techniques:** T1078 (Valid Accounts), T1566 (Phishing / Potential AiTM).
* **Skills Applied:** KQL data binning, identifying MFA bypass attempts, isolating suspicious proxy infrastructure.
* 🔗 **[View Full Investigation](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/3.log-analysis/entra-id/EntraID-Impossible-Travel.md)**

### 3. Threat Hunting: OS Credential Dumping (LSASS) & Data Exfiltration
* **Objective:** Triage a multi-stage attack involving memory extraction from `explorer.exe` (bypassing LSASS restrictions) and data exfiltration.
* **Techniques:** T1003 (OS Credential Dumping), T1048 (Exfiltration Over Alternative Protocol).
* **Skills Applied:** Sysmon Event ID 10 analysis, Procdump execution tracking, PowerShell ScriptBlock logging (Event ID 4104).
* 🔗 **[View Full Investigation](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/2.investigations/06-true-positive-procdump-exfiltration.md)**

### 4. False Positive Tuning: High-Velocity Group Enumeration
* **Objective:** Differentiate adversary reconnaissance (BloodHound) from legitimate Anti-Malware scanning activity to reduce SIEM alert fatigue.
* **Techniques:** T1069 (Permission Groups Discovery).
* **Skills Applied:** Windows Security Event ID 4798 analysis, baselining known-good behaviour, defining high-fidelity exclusion logic.
* 🔗 **[View Full Investigation](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/2.investigations/04-false-positive-event4798.md)**

### 5. Ransomware Emulation & FIM (Supply Chain Impact)
* **Objective:** Simulate a localized ransomware infection targeting critical logistics data (Perpetual Inventory & Good Faith Receiving) and detect the encryption process in real-time.
* **Techniques:** T1486 (Data Encrypted for Impact).
* **Skills Applied:** Wazuh File Integrity Monitoring (Syscheck) configuration, custom Python payload execution, and rapid alert triage of mass file modifications.

 * 🔗 **[View Ransomware & FIM Analysis](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/5.projects/wazuh-ransomware-fim/README.md)**

---

## 🔺 Detection Engineering & Active Defence

Moving beyond reactive analysis, I develop custom rules and proactive defence mechanisms to identify specific adversarial behaviours.

* 📄 **[Sigma Rule: Malicious Registry Modification for Persistence](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/1.detections/3.rules/sigma/registry-modification-persistence-tracking.yml)**
* 📄 **[KQL Query: Suspicious PowerShell Encoded Command Execution](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/1.detections/3.rules/sigma/suspicious-powershell-execution.yml)**
* 🍯 **[Active Defence: Honeytokens & Cyber Deception Playbook](https://github.com/magda-uk/soc-analyst-portfolio/blob/main/4.hunting/active-defence-honeytokens/active-defence-honeytokens.md)**

---



## 🔺 Phishing Incident Response & Artefact Triage
A dedicated laboratory environment focused on the end-to-end triage of phishing campaigns and the safe handling of malicious artefacts. This project demonstrates core Blue Team capabilities in email security, threat actor infrastructure analysis, and Social Engineering investigation.

* 🔗  **[View the Phishing Incident Response Lab ](https://github.com/magda-uk/phishing-incident-response-lab)**

### 1. Suspicious Invoice: Artefact Triage & Social Engineering
* **Objective**: Conduct safe static analysis of a malicious PDF artefact impersonating a legitimate financial entity (Santander / inFakt.pl).

* **Techniques**: T1566.001 (Spearphishing Attachment), T1036 (Masquerading).

* **Skills Applied**: Safe evidence handling, static analysis, extraction of Indicators of Compromise (IoCs), and identifying expected sandbox detonation behaviours.

### 2. Email Header Analysis & Spoofing Detection
* **Objective**: Perform a deep-dive investigation of email routing metadata to verify sender authenticity and uncover the attacker's true origin infrastructure.

* **Techniques**: T1566.002 (Spearphishing Link), T1586 (Compromise Accounts).

* **Skills Applied**: Analysing SMTP routing hops, validating SPF/DKIM/DMARC alignment, and extracting malicious sender IP/Domain metadata for threat intelligence enrichment.

## 🔺 Connect with me

I am actively seeking an L1 SOC Analyst position where I can bring my structured troubleshooting and log analysis skills to a dedicated security team.

* **LinkedIn:** [linkedin.com/in/magda-d-infosec](https://www.linkedin.com/in/magda-d-infosec)