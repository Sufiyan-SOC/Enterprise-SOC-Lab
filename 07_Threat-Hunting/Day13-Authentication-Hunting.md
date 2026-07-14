# Authentication Hunting Methodology

## Objective

Identify suspicious authentication activity using Windows Security logs.

---

## Hunting Workflow

1. Review successful logons.
2. Review failed logons.
3. Compare authentication frequency.
4. Validate user account.
5. Verify logon type.
6. Investigate repeated failures.
7. Correlate with endpoint activity.

---

## Hunt Questions

* Which users failed authentication?
* Which accounts logged in successfully?
* Were failures followed by successful logons?
* Was Remote Desktop used?
* Is the activity expected?

---

## Indicators

* Multiple failed logons
* New administrative accounts
* Unusual logon types
* Authentication outside business hours

---

## MITRE ATT&CK

T1078 – Valid Accounts
