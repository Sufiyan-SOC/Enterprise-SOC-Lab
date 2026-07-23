# Day 36 Analysis

## Objective

Detect Windows network share discovery commands executed during reconnaissance.

---

## Findings

Windows share enumeration generated Sysmon Process Creation events.

Splunk successfully detected the execution of network discovery commands and identified the associated user, endpoint, and command line.

---

## Lessons Learned

Network share discovery is commonly performed during the Discovery phase before lateral movement. Monitoring these commands provides early visibility into attacker reconnaissance.
