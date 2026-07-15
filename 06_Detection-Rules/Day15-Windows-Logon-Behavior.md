# Detection Name

Windows Logon Behavior Analysis

---

## Detection Purpose

Detect abnormal Windows authentication behavior through logon activity analysis.

---

## MITRE ATT&CK

Technique: **T1078 – Valid Accounts**

---

## Data Source

Windows Security Logs

Event IDs:

* 4624
* 4625

---

## Detection Logic

Review authentication behavior by analyzing:

* Logon frequency
* Logon type
* Failed authentication
* Successful authentication

---

## Splunk Detection Query

```spl
index=* (EventCode=4624 OR EventCode=4625)
| stats count by Account_Name EventCode
```

---

## Severity

Medium

---

## False Positives

* Password mistakes
* Service accounts
* Administrative logons

---

## Triage Steps

1. Review authentication history.
2. Identify repeated failures.
3. Validate logon type.
4. Review endpoint activity.

---

## Recommended Analyst Actions

* Investigate abnormal authentication patterns.
* Correlate with endpoint events.
* Escalate suspicious authentication activity.
