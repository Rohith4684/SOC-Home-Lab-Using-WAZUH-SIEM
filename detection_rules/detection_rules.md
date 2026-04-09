# Detection Rules (Wazuh)

This section documents the custom detection rules created in the SOC home lab.

---

## Rule Location

All custom rules are stored in:

```text
/var/ossec/etc/rules/local_rules.xml
```

---

## 1. Brute Force Detection

### Purpose

Detect multiple failed login attempts within a short time.

---

### Rule

```xml id="p4g9tw"
<group name="authentication,bruteforce">

  <rule id="100002" level="10" frequency="3" timeframe="120">
    <if_matched_sid>60122</if_matched_sid>
    <description>Brute force attack detected (multiple login failures)</description>
    <mitre>
      <id>T1110</id>
    </mitre>
  </rule>

</group>
```

---

### Logic

```text
3 failed logins within 120 seconds → trigger alert
```

---

### Detection Type

* Behavior-based
* Correlation rule

---

## 2. Possible Account Compromise Detection

### Purpose

Detect successful login after brute force attempts.

---

### Rule

```xml id="fqk3gk"
<group name="authentication,compromise">

  <rule id="100010" level="12">
    <if_sid>60106</if_sid>
    <if_matched_sid>100002</if_matched_sid>
    <description>Login success after brute force (possible compromise)</description>
    <mitre>
      <id>T1078</id>
    </mitre>
  </rule>

</group>
```

---

### Logic

```text
Brute force detected → then login success → possible compromise
```

---

### Detection Type

* Multi-stage correlation
* High severity alert

---

## 3. Account Discovery Detection

### Purpose

Detect enumeration commands like `net user`.

---

### Rule

```xml id="rq3g2k"
<group name="discovery,account">

  <rule id="100130" level="7">
    <if_sid>92031</if_sid>
    <match>net user|net1 localgroup</match>
    <description>Account discovery command detected</description>
    <mitre>
      <id>T1087</id>
    </mitre>
  </rule>

</group>
```

---

### Logic

```text
Command contains "net user" → flag as discovery activity
```

---

### Detection Type

* Command-based detection

---

## Key Learnings

* Detection is not just single events → requires correlation
* Small XML errors can break rule execution
* Testing rules is essential after writing
* MITRE mapping helps understand attacker behavior

---

## Common Issues Faced

* Incorrect XML structure
* Duplicate rule IDs
* Manager service failing due to syntax errors
* Rules not triggering due to wrong conditions

---

## Next Improvements

* Add more MITRE techniques
* Reduce false positives
* Build advanced correlation chains
* Integrate external threat intelligence

---
