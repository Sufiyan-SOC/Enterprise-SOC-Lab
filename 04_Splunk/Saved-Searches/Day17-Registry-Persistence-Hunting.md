# Saved Searches

## Registry Run Key Detection

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
(TargetObject="*\\CurrentVersion\\Run\\*" OR TargetObject="*\\CurrentVersion\\RunOnce\\*")
```

Purpose:
Quickly identify Registry Run and RunOnce persistence.

---

## Registry Timeline

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" SOCLabTest
| sort _time
```

Purpose:
Review Registry activity in chronological order.
