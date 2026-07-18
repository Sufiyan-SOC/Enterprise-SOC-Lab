# Hunt Name

Windows User Account Hunting

---

## Hunt ID

TH-013

---

## Objective

Identify unauthorized Windows user account creation.

---

## Threat Hypothesis

An attacker may create a new local administrator account to maintain access after compromising a system.

---

## Required Data Sources

* Windows Security Logs
* Event ID 4720

---

## MITRE ATT&CK

* T1098 – Account Manipulation
* T1078 – Valid Accounts

---

## Hunt Query

```spl
index=* source="WinEventLog:Security" EventCode=4720
| table _time ComputerName Account_Name SubjectUserName
```

---

## Normal Output

* Administrator creates a temporary lab account.
* Account follows organizational naming standards.
* Business-hours administrative activity.

---

## Suspicious Output

* Unknown administrator account.
* Account created by SYSTEM.
* Account created outside business hours.
* Unexpected privileged user creation.

---

## IOC Examples

* Random account names.
* Hidden administrator accounts.
* Unauthorized local admin creation.
* Multiple account creation events in a short period.

---

## Analyst Outcome

The analyst should determine whether the account creation is legitimate, correlate with authentication events, review privilege assignments, and escalate unauthorized account creation.

---

## Investigation Guidance

Correlate Event ID 4720 with:

* Event ID 4624 (Successful Logon)
* Event ID 4672 (Special Privileges Assigned)
* Sysmon Event ID 1 (Process Creation)

to identify who created the account and whether the activity is part of a broader attack.

---

## References

* MITRE ATT&CK T1098
* MITRE ATT&CK T1078
* Microsoft Security Event Documentation
