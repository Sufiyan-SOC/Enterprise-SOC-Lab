# Scheduled Task Persistence Detection

## Objective

Detect Windows Scheduled Task creation using Microsoft Sysmon process creation events.

---

## Data Source

Microsoft Sysmon

Process Creation Events

---

## Detection Strategy

Monitor execution of:

* schtasks.exe

Validate:

* User account
* Parent process
* Task name
* Execution context

Investigate tasks that launch:

* powershell.exe
* cmd.exe
* mshta.exe
* rundll32.exe
* Executables from user-writable directories

---

## False Positives

* Administrative maintenance
* Enterprise software deployment
* Scheduled automation
* Operating system tasks

---

## Severity

High

---

## MITRE ATT&CK

T1053.005 – Scheduled Task / Job
