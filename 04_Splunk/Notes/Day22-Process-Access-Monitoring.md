# Process Access Monitoring

## Purpose

Process Access monitoring helps identify when one process attempts to access another process. This visibility is useful for detecting credential dumping, process injection, privilege abuse, and post-exploitation techniques.

## Sysmon Event

Event ID 10 – Process Access

## Important Fields

* SourceImage
* TargetImage
* GrantedAccess
* User

## SOC Investigation Focus

* LSASS access
* Unexpected process interactions
* High privilege access requests
* Unknown executables accessing sensitive processes
* Process injection indicators
