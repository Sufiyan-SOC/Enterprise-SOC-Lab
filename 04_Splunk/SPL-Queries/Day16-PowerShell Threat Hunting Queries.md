# PowerShell Threat Hunting Queries

## 1. Find all PowerShell executions

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1 Image="*powershell.exe"
```

Purpose:
Detect every PowerShell process creation event.

---

## 2. PowerShell Investigation

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1 Image="*powershell.exe"
| table _time Image ParentImage CommandLine User Computer
```

Purpose:
Display investigation-relevant fields.

---

## 3. Hunt Suspicious PowerShell Parameters

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1
(CommandLine="*-enc*" OR CommandLine="*-EncodedCommand*" OR CommandLine="*-ExecutionPolicy*" OR CommandLine="*-nop*" OR CommandLine="*-w hidden*")
| table _time User ParentImage CommandLine
```

Purpose:
Search for commonly abused PowerShell parameters.

---

## 4. Parent Process Analysis

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1 Image="*powershell.exe"
| stats count by ParentImage
| sort -count
```

Purpose:
Identify which processes launch PowerShell.

---

## 5. PowerShell Activity Trend

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1 Image="*powershell.exe"
| timechart span=15m count
```

Purpose:
Visualize PowerShell execution over time.
