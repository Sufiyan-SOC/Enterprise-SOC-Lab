# Windows Discovery Activity Dashboard

## Objective

Provide SOC analysts with visibility into account discovery activity across Windows endpoints.

---

## Dashboard Panels

### Discovery Commands

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| stats count by Image
```

---

### Top Users

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| stats count by User
```

---

### Timeline

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| timechart span=5m count
```
