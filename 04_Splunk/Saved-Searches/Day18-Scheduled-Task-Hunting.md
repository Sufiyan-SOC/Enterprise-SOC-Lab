# Saved Searches

## Scheduled Task Detection

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" Image="*schtasks.exe"
```

Purpose:

Quickly identify Scheduled Task creation activity.

---

## Timeline Correlation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
(Image="*schtasks.exe" OR Image="*reg.exe" OR Image="*powershell.exe")
| sort _time
```

Purpose:

Review persistence-related administrative activity in chronological order.
