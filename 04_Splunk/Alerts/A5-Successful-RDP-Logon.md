# Alert

## Alert Information

| Field | Value |
|-------|-------|
| Alert Name | Successful RDP Logon Detected |
| Status | Active |
| Severity | Medium |
| Platform | Splunk Enterprise |
| Log Source | Windows Security Log |
| Event ID | 4624 |

---

# Objective

Detect successful Remote Desktop Protocol (RDP) logons that may indicate legitimate administration or potential lateral movement.

---

# Trigger Condition

- Event ID = 4624
- Logon Type = 10

---

# SPL

```spl
index=* source="WinEventLog:Security" EventCode=4624 LogonType=10
| table _time ComputerName Account_Name Source_Network_Address WorkstationName
```

---

# Analyst Action

- Verify source IP
- Verify destination endpoint
- Validate user account
- Review authentication timeline
