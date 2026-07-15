# Registry Persistence Hunting

## Objective

Identify Registry-based persistence mechanisms using Sysmon.

---

## Hunting Workflow

1. Detect Registry Value Set events.
2. Identify Run and RunOnce modifications.
3. Review the responsible process.
4. Validate Registry value data.
5. Correlate with PowerShell execution.
6. Correlate with Scheduled Task activity.
7. Build a complete persistence timeline.

---

## Hunting Questions

* Which Registry path changed?
* Is it a persistence location?
* Which process modified the Registry?
* Who performed the action?
* Was PowerShell executed before the modification?

---

## Common Indicators

* Run Key modifications
* RunOnce modifications
* PowerShell followed by Registry changes
* Persistence after user logon

---

## MITRE ATT&CK

T1547.001 – Registry Run Keys / Startup Folder
