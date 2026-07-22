# Alert

## Alert Information

| Field | Value |
|-------|-------|
| Alert Name | Windows Service Creation Detected |
| Status | Active |
| Severity | High |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect creation of Windows services that may indicate persistence or privilege escalation activity.

---

# Trigger Condition

Monitor execution of **sc.exe** with the **create** argument.

---

# SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
Image="*\\sc.exe"
| search CommandLine="*create*"
| table _time Computer User ParentImage Image CommandLine
```

---

# Analyst Action

- Identify endpoint
- Verify user
- Review created service
- Investigate parent process
- Determine if activity is authorized
