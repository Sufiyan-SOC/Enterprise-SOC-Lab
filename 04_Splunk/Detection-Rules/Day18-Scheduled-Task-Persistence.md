# Scheduled Task Persistence Detection

## Objective

Detect creation and execution of Windows Scheduled Tasks that may indicate persistence.

---

## Data Source

* Microsoft Sysmon
* Process Creation Events

---

## Detection Logic

Monitor execution of:

* schtasks.exe

Investigate:

* User
* Parent Process
* Computer
* Task Name
* Trigger
* Executable Path

---

## Detection Query

Reference:

Scheduled-Task-Hunting.md → Generic Scheduled Task Detection

---

## High-Risk Indicators

Investigate tasks that launch:

* powershell.exe
* cmd.exe
* wscript.exe
* cscript.exe
* mshta.exe
* rundll32.exe

Or executables located in:

* %Temp%
* %AppData%
* C:\Users\Public

---

## False Positives

* Windows Administrative Tasks
* IT Automation
* Software Installation
* Enterprise Management Tools

---

## Investigation Steps

1. Verify task creator.
2. Review execution context.
3. Validate executable path.
4. Inspect task trigger.
5. Correlate with Registry and PowerShell activity.

---

## MITRE ATT&CK

T1053.005 – Scheduled Task / Job
