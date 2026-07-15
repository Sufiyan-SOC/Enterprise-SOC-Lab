# Hunt Name

Windows Logon Behavior Hunting

---

## Objective

Identify abnormal Windows logon behavior that may indicate unauthorized access.

---

## Threat Hypothesis

An attacker may use valid credentials to authenticate using uncommon logon types or unusual authentication patterns.

---

## Required Data Sources

* Windows Security Logs

---

## MITRE ATT&CK

T1078 – Valid Accounts

---

## Hunt Procedure

1. Review authentication frequency.
2. Identify repeated failed logons.
3. Compare successful authentication.
4. Validate logon types.
5. Investigate user activity.

---

## Hunt Query

```spl
index=* (EventCode=4624 OR EventCode=4625)
| stats count by Account_Name EventCode
```

---

## Expected Findings

* User authentication statistics
* Logon behavior
* Authentication trends

---

## IOC Examples

* Unusual logon types
* Excessive authentication failures
* Authentication from unexpected systems

---

## Investigation Guidance

Validate authentication behavior against normal user activity and correlate with endpoint telemetry before escalating.
