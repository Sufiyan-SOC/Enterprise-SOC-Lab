# Saved Searches

## Successful Authentication

```spl
index=* EventCode=4624
```

Purpose:

Review successful Windows logons.

---

## Failed Authentication

```spl
index=* EventCode=4625
```

Purpose:

Review failed Windows logons.

---

## Logon Type Statistics

```spl
index=* EventCode=4624
| stats count by Logon_Type
```

Purpose:

Summarize authentication methods used across the environment.
