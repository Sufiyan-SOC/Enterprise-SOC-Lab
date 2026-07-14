# Incident Report

## Incident Title

Windows Authentication Investigation

---

## Summary

Windows authentication logs were reviewed to identify successful and failed logon events. Authentication activity was analyzed using Splunk to validate user access and establish a baseline for future investigations.

---

## Data Source

Windows Security Logs

---

## Events Reviewed

* Event ID 4624
* Event ID 4625

---

## Investigation Findings

* Successful authentication events were identified.
* Failed authentication events were reviewed.
* User accounts and logon types were validated.
* No evidence of brute-force activity was observed during the lab.

---

## Severity

Low

Controlled Lab Activity

---

## MITRE ATT&CK

T1078 – Valid Accounts

---

## Analyst Conclusion

Authentication events matched expected laboratory activity. No suspicious authentication behavior or unauthorized access attempts were identified.
