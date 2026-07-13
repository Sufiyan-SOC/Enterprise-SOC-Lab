# Registry Run Key Persistence Detection

## Objective

Detect Registry Run and RunOnce persistence using Sysmon Event ID 13.

---

## Data Source

* Sysmon Operational Log
* Event ID 13 (Registry Value Set)

---

## Detection Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
(TargetObject="*\\CurrentVersion\\Run\\*" OR TargetObject="*\\CurrentVersion\\RunOnce\\*")
| table _time Computer User Image TargetObject Details
```

---

## Investigation Checklist

Verify:

* User
* Computer
* Image
* Registry Path
* Registry Value

---

## Investigate If

Registry value launches:

* powershell.exe
* cmd.exe
* wscript.exe
* mshta.exe
* rundll32.exe

Or points to:

* %AppData%
* %Temp%
* C:\Users\Public

---

## MITRE ATT&CK

T1547.001 – Registry Run Keys / Startup Folder
