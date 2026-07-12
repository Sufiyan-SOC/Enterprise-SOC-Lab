# Saved Searches

## PowerShell Process Creation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1 Image="*powershell.exe"
```

Purpose:

Quickly identify PowerShell execution across monitored endpoints.

---

## Parent Process Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1 Image="*powershell.exe"
| stats count by ParentImage
| sort -count
```

Purpose:

Identify the process responsible for launching PowerShell.
