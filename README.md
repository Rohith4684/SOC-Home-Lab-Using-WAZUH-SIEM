# 🛡️ SOC Home Lab using Wazuh

This project documents the setup and operation of a **Security Operations Center (SOC) home lab** using Wazuh. The goal was to move beyond just installing tools and actually understand how detection, logging, and investigation work in a real environment.

---

## 🎯 Objective

* Build a working SIEM lab from scratch
* Understand how logs are generated and processed
* Create custom detection rules
* Simulate attacker behavior and analyze it
* Learn how SOC analysts investigate events

---

## 🧩 Architecture Overview

The lab consists of three main components:

* **Wazuh Server (Ubuntu VM)** → SIEM (Manager + Indexer + Dashboard)
* **Windows Endpoint** → Log source (Wazuh Agent + Sysmon)
* **Kali Linux** → Attacker machine for simulation

### 🔄 Data Flow

```
Attacker (Kali)
      ↓
Windows Endpoint
      ↓
Wazuh Agent
      ↓
Wazuh Manager
      ↓
Wazuh Indexer
      ↓
Wazuh Dashboard
```

---

## ⚙️ Setup Summary

* Installed Wazuh (all-in-one deployment) on Ubuntu VM
* Connected Windows system as an agent
* Integrated Sysmon for detailed telemetry
* Configured log collection and verified dashboard visibility

For full setup steps, refer to:
📁 `setup/installation_steps.md`

---

## 🔥 Attack Simulations

The following scenarios were simulated to test detection:

* Brute force login attempts
* Account discovery (`net user`, `whoami`)
* PowerShell execution
* Network scanning using Kali Linux

Details available in:
📁 `attack-scenarios/attack_scenarios.md`

---

## 🛡️ Detection Rules Implemented

Custom rules were created to detect:

* **Brute force attacks** (multiple failed logins)
* **Possible account compromise** (fail → success pattern)
* **Account discovery activity**

Rules are documented here:
📁 `detection-rules/detection_rules.md`

---

## 🔍 Log Analysis

* Analyzed logs using Wazuh dashboard
* Observed command-line activity and process behavior
* Mapped detections to **MITRE ATT&CK techniques**
* Practiced reading events as a timeline instead of isolated alerts

Sample logs:
📁 `logs/sample_logs.md`

---

## 📸 Screenshots

This project includes screenshots showing:

* Dashboard overview
* Agent connectivity
* Security alerts (brute force detection)
* Log analysis (command-line details)
* Custom rule configuration
* Attack simulation from Kali

📁 Available in: `screenshots/`

---

## 🧠 Key Learnings

* Detection depends on log availability
* SIEM works on patterns, not single events
* Correlation is essential for meaningful alerts
* Small configuration errors can break the system
* Debugging is a major part of real SOC work

---

## ⚠️ Challenges Faced

* XML syntax errors breaking Wazuh manager
* Agent connectivity issues
* Network configuration problems between VMs
* Understanding correlation rules and tuning them

---

## 🚀 Outcome

This project helped me understand the full SOC workflow:

```
Attack → Log Generation → Detection → Investigation
```

It shifted my focus from just running tools to actually understanding how security monitoring works in practice.

---

## 🔄 Future Improvements

* Add more advanced detection rules
* Simulate more realistic attack scenarios
* Integrate threat intelligence
* Improve correlation and reduce false positives

---

## 📌 Conclusion

This SOC lab is a hands-on approach to learning cybersecurity fundamentals. It provides practical exposure to detection engineering, log analysis, and attacker behavior — bridging the gap between theory and real-world security operations.

---
