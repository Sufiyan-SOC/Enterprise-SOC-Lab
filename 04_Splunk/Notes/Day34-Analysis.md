# Day 34 Analysis

## Objective

Detect Windows service creation using Sysmon process creation logs.

---

## Findings

Execution of **sc.exe** with the **create** argument generated Microsoft Sysmon Event ID 1.

Splunk successfully detected the service creation command and correlated user, endpoint, and command-line information.

---

## Lessons Learned

Windows service creation is frequently abused by attackers to establish persistence. Monitoring service creation commands provides early visibility into suspicious administrative activity.
