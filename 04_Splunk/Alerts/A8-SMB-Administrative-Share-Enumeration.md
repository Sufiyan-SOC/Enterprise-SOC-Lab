# Alert

## Alert Information

| Field | Value |
|-------|-------|
| Alert Name | SMB Administrative Share Enumeration Detected |
| Status | Active |
| Severity | Medium |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect execution of Windows network share discovery commands that may indicate reconnaissance activity before lateral movement.

---

# Trigger Condition

Detect execution of:

- net view
- net use
- net share

---

# SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
(Image="*\\net.exe" OR Image="*\\cmd.exe")
| search CommandLine="*net*"
```

---

# Analyst Action

- Identify user
- Review executed command
- Validate endpoint
- Determine if activity is authorized
