# Registry Hunting Methodology

## Objective

Identify suspicious Registry modifications that may indicate persistence or malicious configuration changes.

---

## Hunting Workflow

1. Verify Registry events.
2. Identify modified Registry paths.
3. Review the responsible process.
4. Validate Registry values.
5. Confirm the user context.
6. Correlate Registry activity with other endpoint events.

---

## Hunting Questions

* Which Registry keys changed?
* Which process performed the modification?
* Was the Registry value expected?
* Is the modified location commonly abused?
* Does the activity align with normal administration?

---

## Common Indicators

* Unexpected Registry modifications
* Suspicious executables
* User profile Registry changes
* Persistence-related Registry locations

---

## MITRE ATT&CK

T1112 – Modify Registry
