# Incident Report

## Incident Title

Windows Logon Investigation

---

## Summary

Windows authentication events were analyzed to understand user logon behavior. Successful and failed authentication events were reviewed to validate user activity and establish a baseline for future anomaly detection.

---

## Data Source

Windows Security Logs

Event IDs:

* 4624
* 4625

---

## Investigation Findings

* Successful logon events were validated.
* Failed authentication attempts were reviewed.
* User accounts and authentication methods were analyzed.
* Authentication activity matched expected laboratory behavior.

---

## Severity

Low

Controlled Laboratory Activity

---

## MITRE ATT&CK

T1078 – Valid Accounts

---

## Analyst Conclusion

Authentication analysis confirmed expected Windows logon activity. No indicators of brute-force attacks, credential misuse, or unauthorized authentication were identified during the investigation.
