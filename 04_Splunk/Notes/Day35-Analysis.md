# Day 35 Analysis

## Objective

Detect remote command execution performed through Impacket PsExec.

---

## Findings

Impacket PsExec executed a remote command on CLIENT1 under the NT AUTHORITY\SYSTEM context.

Microsoft Sysmon Event ID 1 captured the process creation, including the randomly generated parent executable, destination endpoint, and executed command.

Splunk successfully detected the activity and correlated the relevant process information.

---

## Lessons Learned

Remote command execution is a common post-exploitation technique used for lateral movement.

Monitoring SYSTEM-level command execution and unusual parent processes can significantly improve detection capabilities.
