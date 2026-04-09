# SOC-Home-Lab-Using-WAZUH-SIEM
## Overview

This project presents a practical Security Operations Center (SOC) lab built using Wazuh SIEM. The main focus is to detect, analyze, and correlate security events so they form a clear understanding of attack behavior instead of viewing logs individually.

The lab simulates real-world attack scenarios and emphasizes analyzing patterns over time.

---

## Objectives

* Set up a working SOC lab using Wazuh
* Simulate common attack scenarios
* Create custom detection rules
* Correlate multiple events to detect real threats
* Understand logs as a timeline rather than isolated entries

---

## Architecture

The lab setup includes:

* Wazuh Manager – Central system for collecting and analyzing logs
* Agent Machine (Windows/Linux) – Generates system and security logs
* Attacker Machine (Kali Linux) – Used to simulate attacks
* Virtualization – VirtualBox or VMware

---

## Attack Scenarios Simulated

### 1. Brute Force Attack

* Multiple failed login attempts were generated
* Detection is based on repeated failures within a short time period

### 2. Successful Login After Failures

* Sequence observed:

  * Multiple failed logins
  * Followed by a successful login
* This indicates possible credential compromise

### 3. Post-Compromise Activity

* Command execution
* System discovery actions

---

## Detection Engineering

### Custom Rule – Brute Force Detection

* Detects repeated failed login attempts
* Triggers an alert when a defined threshold is crossed

### Correlation Rule – Compromise Detection

* Connects:

  * Failed login attempts
  * Successful login event
* Helps identify suspicious login patterns

---

## Key Learning

Detection is not about a single event. It is about connecting multiple events over time.

This project demonstrates how analyzing logs as a sequence helps in identifying real attack behavior.

---

## Example Attack Timeline

1. Multiple failed login attempts
2. Successful login from the same source
3. Command execution
4. System discovery activity

This sequence suggests a possible system compromise.

---

## Incident Analysis (Sample)

### Summary

A brute-force attack was simulated, followed by a successful login and further activity that indicates a possible compromise.

### Indicators of Compromise (IOCs)

* High number of failed login attempts
* Successful login after failures
* Unusual command execution

### Detection Method

* Custom Wazuh rules
* Correlation between login events

### Conclusion

The SIEM successfully detected and linked multiple events to identify a multi-stage attack.

---

## Tools and Technologies Used

* Wazuh SIEM
* Kali Linux
* VirtualBox or VMware
* Windows and Linux systems

---

## Project Structure

```
SOC-Home-Lab-Using-WAZUH-SIEM/
│
├── README.md
├── architecture/
├── setup/
├── detection-rules/
├── attack-scenarios/
├── logs/
├── screenshots/
└── reports/
```

---

## Screenshots

Screenshots of the Wazuh dashboard, alerts, and logs are available here.

---

## Setup Guide

Detailed setup steps are available in the setup folder.

---

## Future Improvements

* Add MITRE ATT&CK mapping
* Simulate advanced attacks such as privilege escalation and persistence
* Improve alerting and reporting
* Enhance dashboards

---

## Use Case

This project reflects real SOC analyst responsibilities such as:

* Log analysis
* Threat detection
* Event correlation
* Incident investigation

---

## Author
S Rohith Kumar
Final Year B.Tech Computer Science Student
Specialization: Cybersecurity

---
