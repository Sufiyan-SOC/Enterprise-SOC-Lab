# PowerShell Hunting Notes

## Overview

PowerShell is a legitimate Windows administration tool widely used by system administrators for automation and management. Because of its flexibility and deep access to the operating system, it is also frequently abused by attackers.

Monitoring PowerShell execution is a common SOC activity for detecting suspicious behavior.

---

# Data Source

* Sysmon Operational Log
* Event ID: 1 (Process Creation)

---

# Key Fields

| Field       | Purpose                            |
| ----------- | ---------------------------------- |
| Image       | Executed process path              |
| ParentImage | Process that launched PowerShell   |
| User        | User account executing the process |
| Computer    | Endpoint where execution occurred  |
| _time       | Event timestamp                    |

---

# Normal Parent Processes

The following parent processes are commonly observed during legitimate PowerShell usage:

* explorer.exe
* cmd.exe
* powershell_ise.exe

These should still be validated within the environment.

---

# Parent Processes Requiring Investigation

PowerShell launched by the following processes may indicate suspicious activity:

* winword.exe
* excel.exe
* outlook.exe
* wscript.exe
* cscript.exe
* mshta.exe
* rundll32.exe

These processes should always be reviewed during investigations.

---

# SOC Investigation Checklist

When investigating PowerShell activity:

* Identify the user account.
* Verify the parent process.
* Review execution frequency.
* Compare against normal administrative activity.
* Correlate with additional Windows or Sysmon events.

---

# MITRE ATT&CK

Technique:

T1059.001 – PowerShell

---

# Key Takeaways

* PowerShell execution alone is not malicious.
* Parent process provides valuable execution context.
* Multiple PowerShell executions in a short period may require investigation.
* Context is more important than the executable name itself.
