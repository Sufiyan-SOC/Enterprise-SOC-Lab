# Saved Searches

## Authentication Monitoring

```spl
index=* (EventCode=4624 OR EventCode=4625)
```

Purpose:

Monitor Windows authentication activity.

---

## Failed Authentication

```spl
index=* EventCode=4625
```

Purpose:

Quickly identify failed logon attempts.

---

## Successful Authentication

```spl
index=* EventCode=4624
```

Purpose:

Review successful user logons.
