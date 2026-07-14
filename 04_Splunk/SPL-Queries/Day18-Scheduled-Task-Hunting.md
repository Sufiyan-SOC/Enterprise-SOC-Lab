# Scheduled Task Hunting Queries

## 1. Detect schtasks.exe Execution

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" Image="*schtasks.exe"
| table _time User Computer Image ParentImage
```

Purpose:
Identify execution of the Windows Scheduled Task utility.

---

## 2. Hunt Scheduled Task by IOC

```spl
index=* SOCLabTask
| table _time Image ParentImage CommandLine User Computer
```

Purpose:
Search for a known Scheduled Task name during an investigation.

---

## 3. Generic Scheduled Task Detection

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" Image="*schtasks.exe"
| stats count by User Computer Image ParentImage
| sort -count
```

Purpose:
Summarize Scheduled Task creation activity by user and endpoint.

---

## 4. Timeline Correlation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
(Image="*schtasks.exe" OR Image="*reg.exe" OR Image="*powershell.exe")
| sort _time
| table _time User Image ParentImage Computer
```

Purpose:
Correlate persistence-related administrative activity across multiple Windows utilities.
