# Day 31 Notes

## Objective

Detect Windows account discovery activity.

---

## Findings

The simulated attack generated Sysmon Process Creation events.

The following binaries were observed:

- whoami.exe

- net.exe

The events were successfully forwarded to Splunk Enterprise.

---

## Challenges

No issues observed during log collection.

---

## Lessons Learned

Windows discovery commands are legitimate administrative tools.

Context is required to distinguish administrative activity from attacker reconnaissance.

---

## Improvement

Future detections should correlate account discovery with authentication activity and privilege escalation events.
