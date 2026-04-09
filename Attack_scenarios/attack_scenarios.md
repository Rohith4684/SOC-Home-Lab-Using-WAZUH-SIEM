Attack Scenarios
This section documents the simulated attack scenarios used to test detection capabilities in the SOC lab.

Scenario 1: Brute Force Login Attempts
Steps
Locked the Windows system

Entered incorrect password multiple times

Expected Behavior
Multiple login failure logs generated

Brute force rule triggered

Scenario 2: Account Discovery
Commands used
DOS

net user
whoami
Expected Behavior
Detection of account discovery activity

Alerts mapped to MITRE T1087

Scenario 3: PowerShell Execution
Command
PowerShell

powershell -ExecutionPolicy Bypass -Command "Get-Process"
Expected Behavior
Process execution logs

Suspicious PowerShell detection

Scenario 4: Network Scanning (Kali Linux)
Command
Bash

nmap -sS <target-ip>
Expected Behavior
Multiple connection attempts

Reconnaissance activity

Outcome
These scenarios helped validate detection rules and understand how attacker behavior appears in logs.
