# Day 13 - Windows Authentication Notes

## Windows Authentication Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4634 | Logoff |
| 4648 | Logon Using Explicit Credentials |

---

## Event ID 4624

Represents a successful authentication event.

Common fields:

- Account_Name
- Host
- Logon_Type
- Source_Network_Address
- Workstation_Name
- _time

Typical use cases:

- Verify successful user authentication
- Monitor user activity
- Build authentication timelines
- Detect unusual login patterns

---

## Event ID 4625

Represents a failed authentication attempt.

Common fields:

- Account_Name
- Failure_Reason
- Status
- Sub_Status
- Source_Network_Address
- Workstation_Name
- _time

Typical use cases:

- Detect password guessing attempts
- Identify repeated authentication failures
- Investigate account misuse
- Support brute-force detection

---

## Machine Account

Windows computer accounts end with the `$` symbol.

Example:

```
CLIENT1$
```

Machine accounts are automatically created by Windows and should not be confused with user accounts.

---

## Human User Account

Example:

```
sbish
```

Represents an actual user logging into the system.

---

## Common Logon Types

| Logon Type | Description |
|------------|-------------|
| 2 | Interactive Logon |
| 3 | Network Logon |
| 5 | Service Logon |
| 7 | Workstation Unlock |
| 10 | Remote Interactive (RDP) |

---

## Authentication Timeline

Authentication activity can be visualized over time to identify:

- Login trends
- Authentication spikes
- Repeated failed logins
- Successful logins following multiple failures

---

## Basic Brute Force Detection

Multiple failed logins for the same account within a short period may indicate a brute-force attempt.

Example SPL:

```spl
index=* EventCode=4625
| stats count by Account_Name
| where count>=3
```

---

## Authentication Monitoring Workflow

1. Verify authentication events are being ingested.
2. Review successful logins (4624).
3. Review failed logins (4625).
4. Analyze authentication timeline.
5. Identify the most active users.
6. Identify the most active hosts.
7. Investigate repeated authentication failures.
