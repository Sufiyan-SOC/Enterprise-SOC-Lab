# Analysis Notes

## Objective

Validate detection of suspicious PowerShell execution.

---

## Findings

Sysmon successfully logged PowerShell process creation events.

Splunk indexed the generated telemetry.

Detection rule successfully identified suspicious PowerShell command-line arguments.

Alert generated successfully.

---

## Observations

Parent Process

- explorer.exe

Executed User

- sbish

Indicators

- EncodedCommand
- NoProfile
- Hidden Window

---

## Conclusion

Detection successfully validated.

No false positives observed during controlled testing.
