# PowerShell Hunting Methodology

## Objective

Identify suspicious PowerShell execution that may indicate malicious activity or post-exploitation.

---

## Hunting Workflow

1. Detect PowerShell execution.
2. Identify the executing user.
3. Review the parent process.
4. Validate execution context.
5. Correlate with Registry modifications.
6. Correlate with Scheduled Task activity.
7. Build a complete activity timeline.

---

## Hunting Questions

* Who executed PowerShell?
* What process launched PowerShell?
* Was PowerShell expected?
* Did PowerShell precede persistence activity?
* Were additional Windows utilities executed afterward?

---

## Common Indicators

* Unexpected PowerShell execution
* PowerShell launched by Office applications
* PowerShell launched by scripting engines
* Repeated PowerShell activity
* PowerShell executed from unusual user accounts

---

## MITRE ATT&CK

T1059.001 – PowerShell
