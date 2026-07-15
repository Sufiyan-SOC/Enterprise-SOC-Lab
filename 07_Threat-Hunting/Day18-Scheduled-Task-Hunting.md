# Scheduled Task Hunting Methodology

## Objective

Identify Windows Scheduled Tasks that may indicate persistence or unauthorized automation.

---

## Hunting Workflow

1. Detect schtasks.exe execution.
2. Identify the creating user.
3. Review parent process.
4. Validate task name.
5. Verify executable path.
6. Correlate with PowerShell activity.
7. Correlate with Registry persistence.
8. Build an execution timeline.

---

## Hunting Questions

* Who created the task?
* Was elevation used?
* Which process launched schtasks.exe?
* Does the task execute a trusted binary?
* Is the task consistent with normal administrative activity?

---

## Common Indicators

* PowerShell creating Scheduled Tasks
* Office applications launching schtasks.exe
* Tasks executing from Temp or AppData
* Tasks created by unexpected user accounts
* Multiple persistence mechanisms observed together

---

## MITRE ATT&CK

T1053.005 – Scheduled Task / Job
