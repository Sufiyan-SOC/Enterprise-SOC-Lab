# Windows Logon Hunting Methodology

## Objective

Identify unusual Windows authentication activity through logon behavior analysis.

---

## Hunting Workflow

1. Review successful logons.
2. Review failed logons.
3. Compare authentication frequency.
4. Validate logon types.
5. Review workstation information.
6. Identify authentication anomalies.

---

## Hunting Questions

* Which accounts authenticate most frequently?
* Are failed logons followed by successful logons?
* Which logon types are uncommon?
* Is Remote Desktop being used unexpectedly?
* Does authentication activity match expected user behavior?

---

## Indicators

* Excessive failed logons
* Unusual logon types
* Authentication outside normal hours
* New administrative account activity

---

## MITRE ATT&CK

T1078 – Valid Accounts
