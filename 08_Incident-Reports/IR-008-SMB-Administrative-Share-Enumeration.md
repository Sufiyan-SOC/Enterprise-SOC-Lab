# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-008 |
| Incident Name | SMB Administrative Share Enumeration |
| Severity | Medium |
| Status | Closed |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk detected execution of Windows network share discovery commands used to enumerate SMB shares.

The activity was investigated using Microsoft Sysmon telemetry to identify the user, endpoint, and executed commands.

---

# Investigation Summary

- Share discovery activity confirmed.
- Windows discovery commands identified.
- User and endpoint validated.
- Activity classified as controlled lab simulation.

---

# Business Impact

Network share discovery is commonly performed during reconnaissance before lateral movement.

Current Impact:

Low (Lab Simulation)

---

# Recommendations

- Review unauthorized share enumeration.
- Restrict administrative shares.
- Correlate with authentication and remote execution activity.

---

# Analyst Verdict

Classification: True Positive

Confidence: High
