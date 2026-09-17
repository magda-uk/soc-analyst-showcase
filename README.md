# 🛡️ Magda Dominguez | SOC Analyst Portfolio (Showcase)

**Target Role:** SOC Analyst (L1) / Junior Blue Team Analyst  
**Core Stack:** Microsoft Sentinel, Entra ID, Wazuh SIEM, Sysmon, KQL, Windows Event Logs.

## 🎯 About This Showcase
This repository highlights my top technical investigations, threat triage cases, and detection engineering projects. 

My analytical approach is rooted in my professional background in Perpetual Inventory. Managing continuous stock reconciliation and investigating system discrepancies within a high-volume Chilled Distribution Centre requires a meticulous, evidence-based mindset. I now apply this exact methodology to cybersecurity: tracing anomalous behaviour across multiple systems, separating noise from true positive alerts, and reconstructing attack timelines from raw telemetry.

> 💡 **Note:** This repository is a curated showcase of my highest-fidelity work. For a complete view of my daily hands-on labs, foundational training, and operational playbooks, please visit my [Continuous Learning Repository](LINK_A_TU_REPO_MADRE).

---

## 🔍 Featured Investigations (Threat Triage & Analysis)

### 1. Cloud Identity: Impossible Travel & MFA Anomalies
* **Objective:** Triage Entra ID Sign-in logs to identify credential compromise and geolocation anomalies.
* **Techniques:** T1078 (Valid Accounts), T1566 (Phishing).
* **Skills Applied:** Log analysis in Entra ID, identifying MFA bypass attempts, isolating suspicious IP behaviour.
* 🔗 [View Full Investigation](./1.investigations-and-triage/entra-id-impossible-travel.md)

### 2. Threat Hunting: OS Credential Dumping & Data Exfiltration 
* **Objective:** Triage a multi-stage attack involving memory extraction from `explorer.exe` (bypassing LSASS restrictions) and data exfiltration.
* **Techniques:** T1003 (OS Credential Dumping), T1048 (Exfiltration Over Alternative Protocol).
* **Skills Applied:** Sysmon telemetry analysis, Procdump execution tracking, PowerShell ScriptBlock logging (Event ID 4104).
* 🔗 [View Full Investigation](./1.investigations-and-triage/procdump-exfiltration-analysis.md)

### 3. False Positive Tuning: High-Velocity Group Enumeration (Event ID 4798)
* **Objective:** Differentiate adversary reconnaissance (e.g., BloodHound) from legitimate Anti-Malware scanning activity to reduce alert fatigue.
* **Techniques:** T1069 (Permission Groups Discovery).
* **Skills Applied:** Windows Security Event analysis, baselining known-good behaviour, defining high-fidelity exclusion logic.
* 🔗 [View Full Investigation](./1.investigations-and-triage/false-positive-tuning-4798.md)

---

## 🏗️ SOC Lab Environment & Architecture

### Enterprise Host Monitoring Lab (Wazuh & Sysmon)
I built and maintain a local SIEM environment to generate real attack telemetry, validate custom detection rules, and practice end-to-end incident response.
* **Infrastructure:** Wazuh Manager, Windows 10/11 VM (Agent), Kali Linux VM (Adversary emulation).
* **Host Telemetry:** Sysmon (v14+) configured with a custom SwiftOnSecurity baseline.
* **Capabilities:** EDR telemetry simulation, alerting on malicious PowerShell execution, network scanning detection, and C2 beaconing analysis.
* 🔗 [View Lab Architecture & Rule Validations](./3-soc-labs/wazuh-lab-environment.md)

---

## ⚙️ Detection Engineering & CTI
*Custom correlation rules and threat hunting playbooks developed to identify specific adversarial behaviours.*

* 📄 **[Sigma Rule: Malicious Registry Modification for Persistence](./2-detection-engineering/sigma-registry-persistence.md)**
* 📄 **[KQL Query: Suspicious PowerShell Encoded Command Execution](./2-detection-engineering/kql-encoded-powershell.md)**
* 📄 **[Threat Hunting Playbook: LSASS Memory Access (Event ID 10)](./1.investigations-and-triage/hunting-lsass-access.md)**

---

## 📬 Connect with me
I am actively seeking an L1 SOC Analyst position where I can bring my structured troubleshooting and log analysis skills to a dedicated security team.

🔗 **LinkedIn:** [linkedin.com/in/magda-d-infosec](https://linkedin.com/in/magda-d-infosec)