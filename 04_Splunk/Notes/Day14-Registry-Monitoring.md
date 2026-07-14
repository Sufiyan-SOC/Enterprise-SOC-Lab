# Registry Monitoring

## Overview

Windows Registry stores operating system and application configuration settings. Monitoring Registry modifications helps identify persistence mechanisms, configuration changes, and potentially malicious activity.

---

## Data Source

Microsoft Sysmon

Event ID 13

Registry Value Set

---

## Important Fields

| Field        | Description            |
| ------------ | ---------------------- |
| TargetObject | Modified Registry path |
| Details      | Registry value         |
| Image        | Process responsible    |
| User         | User account           |
| Computer     | Endpoint               |
| _time        | Event timestamp        |

---

## Why Monitor Registry?

Registry monitoring helps detect:

* Persistence
* Malware configuration
* Unauthorized system changes
* Administrative modifications

---

## SOC Investigation Checklist

* Identify modified Registry path.
* Verify responsible process.
* Review Registry value.
* Validate user account.
* Correlate with nearby endpoint activity.
