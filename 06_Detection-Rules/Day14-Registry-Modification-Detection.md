# Registry Modification Detection

## Objective

Detect Windows Registry modifications using Microsoft Sysmon Event ID 13.

---

## Data Source

Microsoft Sysmon

Event ID 13

Registry Value Set

---

## Detection Strategy

Monitor Registry modifications by validating:

* Registry path
* Executing process
* User account
* Registry value
* Endpoint

---

## Investigation Steps

1. Review modified Registry key.
2. Identify responsible process.
3. Validate Registry value.
4. Determine whether the change is expected.
5. Correlate with additional endpoint activity.

---

## False Positives

* Software installation
* Windows updates
* Administrative changes
* Enterprise management tools

---

## Severity

Medium

---

## MITRE ATT&CK

T1112 – Modify Registry
