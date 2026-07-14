# Windows Authentication Detection

## Objective

Detect successful and failed Windows authentication events.

---

## Data Source

Windows Security Logs

Event IDs:

* 4624
* 4625

---

## Detection Logic

Monitor:

* Successful authentication
* Failed authentication
* Multiple failures
* Unusual logon types

---

## Investigation

Review:

* Username
* Host
* Logon Type
* Source IP
* Time

---

## False Positives

* User typing incorrect password
* Service account authentication
* Administrative activity

---

## MITRE ATT&CK

T1078

Valid Accounts
