# Windows Authentication Notes

## Event IDs

4624

Successful Logon

4625

Failed Logon

---

## Why Authentication Logs Matter

Authentication logs help SOC analysts detect:

* Brute-force attacks
* Password spraying
* Unauthorized access
* Privilege abuse
* Lateral movement

---

## Important Fields

* Account_Name
* EventCode
* Logon_Type
* Workstation_Name
* Source_Network_Address
* _time

---

## Common Logon Types

| Type | Description    |
| ---- | -------------- |
| 2    | Interactive    |
| 3    | Network        |
| 5    | Service        |
| 10   | Remote Desktop |

---

## Analyst Checklist

* Verify username.
* Check authentication status.
* Review source workstation.
* Validate logon type.
* Correlate with surrounding events.
