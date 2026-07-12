# PowerShell Execution Detection

## Detection Goal

Detect PowerShell execution using Sysmon Event ID 1.

---

## Data Source

* Microsoft Sysmon
* Event ID 1 (Process Creation)

---

## Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventID=1 Image="*powershell.exe"
| stats count by User ParentImage
```

---

## Analyst Validation

Verify:

* User
* ParentImage
* Host
* Frequency

Expected Parent Process:

* explorer.exe (Normal)

Investigate Further:

* winword.exe
* excel.exe
* outlook.exe
* wscript.exe
* mshta.exe

---

## MITRE ATT&CK

T1059.001 – PowerShell
