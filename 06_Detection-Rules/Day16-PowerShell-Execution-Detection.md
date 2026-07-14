# PowerShell Execution Detection

## Objective

Detect Windows PowerShell execution using Microsoft Sysmon process creation events.

---

## Data Source

Microsoft Sysmon

Process Creation Events

---

## Detection Strategy

Monitor execution of:

* powershell.exe

Validate:

* User account
* Parent process
* Endpoint
* Execution timeline

---

## Investigation Steps

1. Identify the executing user.
2. Review the parent process.
3. Validate whether execution is expected.
4. Correlate with Registry modifications or Scheduled Tasks.
5. Determine whether additional investigation is required.

---

## False Positives

* Administrative automation
* System administration
* Software deployment
* Enterprise management tools

---

## Severity

Medium

---

## MITRE ATT&CK

T1059.001 – PowerShell
