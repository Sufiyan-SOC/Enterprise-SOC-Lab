# Day 32 Analysis

## Objective

Detect Windows network share enumeration.

---

## Findings

The attack generated Microsoft Sysmon Event ID 1.

Splunk successfully detected execution of:

- net share
- net use
- SYSVOL enumeration
- NETLOGON enumeration

---

## Lessons Learned

Network share discovery is commonly observed after initial compromise.

Monitoring Windows native discovery utilities provides early visibility before lateral movement.
