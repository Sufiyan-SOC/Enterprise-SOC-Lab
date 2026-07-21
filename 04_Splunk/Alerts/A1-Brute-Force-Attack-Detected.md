# Brute Force Attack Detected

## Purpose

Detect repeated failed authentication attempts against Windows endpoints.

---

## Data Source

- Windows Security Logs
- Event ID 4625

---

## Trigger Condition

If failed authentication attempts are greater than or equal to 3 for the same user account.

---

## Severity

High

---

## Schedule

Every 5 Minutes

---

## Action

- Generate Splunk Alert
- Notify SOC Analyst
- Begin Investigation

---

## Related MITRE ATT&CK

T1110 - Brute Force
