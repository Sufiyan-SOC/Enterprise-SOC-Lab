# Detection Name

Windows Authentication Monitoring

---

## Detection Purpose

Detect successful and failed Windows authentication events to identify unauthorized access attempts, password guessing, and abnormal user authentication behavior.

---

## MITRE ATT&CK

Technique: **T1078 – Valid Accounts**

---

## Data Source

Windows Security Logs

Event IDs:

* 4624 (Successful Logon)
* 4625 (Failed Logon)

---

## Detection Logic

Monitor successful and failed authentication events.

Investigate:

* Excessive failed logons
* Failed logons followed by successful authentication
* Authentication from unexpected systems
* Unusual logon types

---

## Splunk Detection Query

```spl
index=* (EventCode=4624 OR EventCode=4625)
| table _time host Account_Name EventCode Logon_Type
```

---

## Severity

Medium

---

## False Positives

* User entering incorrect password
* Service account authentication
* Administrative maintenance

---

## Triage Steps

1. Identify affected user account.
2. Review logon type.
3. Verify source workstation.
4. Review authentication timeline.
5. Correlate with endpoint activity.

---

## Recommended Analyst Actions

* Validate user activity.
* Review additional authentication attempts.
* Escalate if suspicious authentication behavior is confirmed.
