# Registry Run Keys

## Overview

Registry Run and RunOnce keys are Windows autorun locations used to automatically start applications after a user logs in. Because of this behavior, they are commonly abused by attackers to establish persistence.

---

## Data Source

* Microsoft Sysmon
* Event ID 13 – Registry Value Set

---

## Common Registry Locations

### Current User

HKCU\Software\Microsoft\Windows\CurrentVersion\Run

HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce

---

### Local Machine

HKLM\Software\Microsoft\Windows\CurrentVersion\Run

HKLM\Software\Microsoft\Windows\CurrentVersion\RunOnce

---

## Important Fields

| Field        | Description                          |
| ------------ | ------------------------------------ |
| TargetObject | Registry path that was modified      |
| Details      | Registry value data                  |
| Image        | Process responsible for modification |
| User         | User account                         |
| Computer     | Endpoint                             |
| _time        | Event timestamp                      |

---

## SOC Investigation Checklist

When a Registry Run Key is modified:

1. Verify the registry path.
2. Identify the responsible process.
3. Review the stored executable.
4. Validate whether the executable is legitimate.
5. Correlate with other endpoint events.

---

## High-Risk Indicators

* powershell.exe
* cmd.exe
* wscript.exe
* mshta.exe
* rundll32.exe

Executables stored under:

* %Temp%
* %AppData%
* C:\Users\Public

should always be investigated.

---

## MITRE ATT&CK

Technique:

T1547.001 – Registry Run Keys / Startup Folder

---

## Key Takeaways

* Registry Run Keys are one of the most common persistence mechanisms.
* Event ID 13 is valuable for detecting Registry modifications.
* Context matters—legitimate software also uses Run Keys.
* Always validate both the executable path and the process responsible for the modification.
