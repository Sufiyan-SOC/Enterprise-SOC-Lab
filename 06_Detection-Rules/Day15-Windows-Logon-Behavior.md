# Windows Logon Behavior Detection

## Objective

Detect abnormal Windows authentication behavior through logon event analysis.

---

## Data Source

Windows Security Logs

Event IDs:

* 4624
* 4625

---

## Detection Strategy

Monitor:

* Failed authentication
* Successful authentication
* Logon type anomalies
* Repeated authentication attempts

---

## Investigation Steps

1. Identify user account.
2. Validate authentication result.
3. Review logon type.
4. Verify workstation.
5. Correlate with surrounding endpoint events.

---

## False Positives

* User password mistakes
* Service account authentication
* Administrative maintenance

---

## Severity

Medium

---

## MITRE ATT&CK

T1078 – Valid Accounts
