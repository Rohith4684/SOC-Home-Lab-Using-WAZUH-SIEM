#  Sample Logs

This section contains example logs generated during attack simulations.

---

## Brute Force Log

```json
{
  "rule.id": "60122",
  "description": "Logon failure",
  "user": "ROHITH",
  "source.ip": "192.168.0.9"
}
```

---

## Account Discovery Log

```json
{
  "commandLine": "net user",
  "process": "cmd.exe",
  "mitre": "T1087"
}
```

---

## PowerShell Execution Log

```json
{
  "process": "powershell.exe",
  "commandLine": "Get-Process"
}
```

---

## Note

Logs were collected using Wazuh agent and enriched with Sysmon data.

---
