# Day 33 Analysis

## Objective

Detect successful Remote Desktop Protocol (RDP) authentication.

---

## Findings

A successful RDP session generated Windows Security Event ID 4624 with Logon Type 10.

Splunk successfully detected the authentication event and correlated user, endpoint, and source IP information.

---

## Lessons Learned

Successful RDP authentication is commonly associated with remote administration but may also indicate attacker lateral movement if performed from unexpected systems or accounts.
