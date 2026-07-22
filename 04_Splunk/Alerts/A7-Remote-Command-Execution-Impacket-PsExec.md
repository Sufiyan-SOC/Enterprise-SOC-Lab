# Alert

## Alert Information

| Field | Value |
|-------|-------|
| Alert Name | Remote Command Execution via Impacket PsExec |
| Status | Active |
| Severity | High |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect remote command execution performed through Impacket PsExec, a tool commonly used by penetration testers and threat actors for lateral movement.

---

# Trigger Condition

- Sysmon Event ID 1
- Process executed as **NT AUTHORITY\SYSTEM**
- Command shell launched remotely

---

# SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
User="NT AUTHORITY\\SYSTEM"
Image="*\\cmd.exe"
| table _time Computer ParentImage Image CommandLine
```

---

# Analyst Action

- Verify source endpoint
- Validate parent process
- Review executed commands
- Correlate with authentication events
- Determine if remote execution was authorized
