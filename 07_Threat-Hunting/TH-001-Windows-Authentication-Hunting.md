# Hunt Name

Windows Authentication Hunting

---

## Objective

Identify suspicious authentication activity across Windows endpoints.

---

## Threat Hypothesis

An attacker may attempt unauthorized access by generating multiple authentication events before successfully logging into a system.

---

## Required Data Sources

* Windows Security Logs

---

## MITRE ATT&CK

T1078 – Valid Accounts

---

## Hunt Procedure

1. Review successful logons.
2. Review failed logons.
3. Compare authentication timeline.
4. Identify unusual users.
5. Verify source systems.

---

## Hunt Query

```spl
index=* (EventCode=4624 OR EventCode=4625)
| table _time host Account_Name EventCode Logon_Type
```

---

## Expected Findings

* Successful logons
* Failed logons
* Authentication timeline

---

## IOC Examples

* Multiple failed logons
* Authentication outside business hours
* New administrative account activity

---

## Investigation Guidance

Review authentication history and validate whether activity matches expected user behavior.
