# SOC Lab Report

## Objective

To build a SOC home lab using Wazuh and understand detection, logging, and attack analysis.

---

## Setup Summary

* Wazuh SIEM deployed on Ubuntu VM
* Windows endpoint connected as agent
* Sysmon integrated for enhanced logging
* Kali Linux used for attack simulation

---

## Key Detections

* Brute force login attempts
* Account discovery activity
* PowerShell execution

---

## Key Learnings

* Detection depends on log availability
* Correlation is required for meaningful alerts
* Small configuration errors can break the system
* Logs must be analyzed as a timeline

---

## Challenges Faced

* XML rule errors causing service failure
* Agent connectivity issues
* Network configuration problems

---

## Conclusion

This project helped in understanding real-world SOC workflows, including detection, analysis, and troubleshooting.

---
