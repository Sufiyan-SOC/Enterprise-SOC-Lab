# Alert

## Alert Information

| Field | Value |
|-------|-------|
| Alert Name | Network Share Discovery Detected |
| Status | Active |
| Severity | Medium |
| Platform | Splunk Enterprise |
| Data Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect execution of Windows network share enumeration commands that may indicate attacker reconnaissance prior to lateral movement.

---

# Trigger Condition

Alert triggers when Windows native commands related to network share discovery are executed.

Monitored Activity

- net share
- net use
- net view
- SYSVOL
- NETLOGON

---

# SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\net.exe" OR Image="*\\cmd.exe")
| eval Discovery=if(
searchmatch("net share") OR
searchmatch("net use") OR
searchmatch("net view") OR
searchmatch("SYSVOL") OR
searchmatch("NETLOGON"),
"Yes","No")
| search Discovery="Yes"
| table _time Computer User Image CommandLine
```

---

# Analyst Action

- Identify endpoint
- Identify user
- Review command execution
- Verify parent process
- Determine if activity is administrative or suspicious
