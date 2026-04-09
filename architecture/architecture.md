# SOC Home Lab Architecture (Wazuh)

This section explains how the SOC home lab is structured and how data flows between components.

---

## Components Used

### 1. Wazuh Server (SIEM)

* Runs on Ubuntu VM
* Includes:

  * Wazuh Manager (log processing)
  * Wazuh Indexer (data storage)
  * Wazuh Dashboard (visualization)

---

### 2. Endpoint (Windows System)

* Acts as the monitored system
* Generates logs based on user/system activity
* Integrated with:

  * Wazuh Agent
  * Sysmon (for detailed telemetry)

---

### 3. Attacker Machine (Kali Linux)

* Used to simulate attacker behavior
* Performs:

  * Network scanning (nmap)
  * Enumeration attempts
  * Basic attack simulations

---

## Data Flow

```text
Kali Linux (Attacker)
        ↓
Windows Endpoint (Target)
        ↓
Wazuh Agent (Log Collection)
        ↓
Wazuh Manager (Processing & Rules)
        ↓
Wazuh Indexer (Storage)
        ↓
Wazuh Dashboard (Visualization)
```

---

## How It Works

1. Attacker or user activity occurs on the Windows machine
2. Logs are generated (Windows logs + Sysmon logs)
3. Wazuh Agent collects and forwards logs
4. Wazuh Manager analyzes logs using rules
5. Alerts are generated if suspicious activity is detected
6. Data is stored in the Indexer and shown in Dashboard

---

## Example Flow

```text
Multiple login failures
        ↓
Wazuh detects pattern (Brute Force)
        ↓
Alert generated (MITRE T1110)
        ↓
Visible in dashboard
```

---

## Purpose of This Architecture

* Simulate real SOC environment
* Understand detection pipelines
* Practice log analysis and investigation
* Bridge gap between theory and real-world monitoring

---

## Key Learning

* Logs are the foundation of detection
* SIEM works based on rules + patterns
* Detection requires both data and context
* Small configuration issues can break the pipeline

---
