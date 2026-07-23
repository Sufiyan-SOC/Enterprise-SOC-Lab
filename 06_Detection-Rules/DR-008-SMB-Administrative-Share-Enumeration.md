# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-007 |
| Rule Name | SMB Administrative Share Enumeration Detection |
| Status | Active |
| Severity | Medium |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect Windows network share discovery commands that may indicate attacker reconnaissance.

---

# Detection Logic

Monitor execution of:

- net view
- net use
- net share

---

# Investigation Steps

1. Identify user.
2. Review executed command.
3. Verify endpoint.
4. Correlate with authentication logs.
5. Determine business justification.

---

# False Positives

- Help Desk
- System Administrators
- Approved troubleshooting

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | Network Share Discovery | T1135 |

---

# Detection Validation

Validated using controlled Windows network share enumeration within the Enterprise SOC Lab.

---

# Analyst Notes

Unexpected network share discovery from standard user accounts should be investigated as possible reconnaissance activity.

---

# Recommendations

- Restrict unnecessary administrative shares.
- Monitor Windows discovery commands.
- Review administrative account usage.
- Correlate with lateral movement attempts.
