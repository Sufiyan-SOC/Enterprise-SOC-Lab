# Local Account Discovery Alert

## Alert Name

Local Account Discovery Detected

---

## Purpose

Detect execution of Windows account discovery and local administrator enumeration commands on enterprise endpoints.

---

## Severity

Medium

---

## Data Source

Microsoft Sysmon

Event ID 1

---

## Trigger Logic

Alert is generated when:

- whoami.exe
- net.exe

are executed.

---

## SPL

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| table _time Computer User Image CommandLine
```

---

## Analyst Action

- Verify user identity
- Review parent process
- Review command line
- Determine whether activity is administrative or suspicious
- Escalate if required
