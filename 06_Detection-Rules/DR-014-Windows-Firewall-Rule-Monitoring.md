# Detection Name

Windows Firewall Rule Monitoring

---

## Detection ID

DR-014

---

## Detection Purpose

Detect unauthorized Windows Firewall rule creation or modification that may indicate defense evasion or persistence.

---

## Detection Type

Behavior-based

---

## Detection Status

Production Ready

---

## MITRE ATT&CK

T1562.004 – Impair Defenses: Disable or Modify System Firewall

---

## Data Source

Windows Firewall Logs

Splunk

---

## Detection Logic

Monitor newly created firewall rules, unexpected inbound allow rules, and rules exposing uncommon ports.

---

## Detection Query

```spl
index=* Firewall
```

---

## Severity

High

---

## Normal Output

```text
DisplayName : SOCLab Firewall Rule

Direction : Inbound

Action : Allow

LocalPort : 5555
```

### Analysis

* Temporary lab rule.
* Created intentionally.
* Expected administrative activity.

**Status:** ✅ Normal

---

## Suspicious Output

```text
DisplayName : Windows Security Update

Direction : Inbound

Action : Allow

LocalPort : 4444
```

### Analysis

* Misleading rule name.
* Unexpected inbound access.
* Common attacker persistence/backdoor pattern.

**Status:** 🚨 High Severity

---

## False Positives

* Software installation
* Helpdesk configuration
* Administrator firewall changes

---

## SOC Investigation Checklist

1. Verify who created the rule.
2. Review the rule name.
3. Validate the opened port.
4. Determine business justification.
5. Correlate with Process Creation events.
6. Escalate unauthorized changes.

---

## Detection Validation

* ☑ Rule Created
* ☑ Event Verified
* ☑ Splunk Query Validated
* ☑ Detection Tested

---

## Detection Confidence

High

Reason:

* Tested in lab
* Splunk detection verified
* Administrative activity validated
