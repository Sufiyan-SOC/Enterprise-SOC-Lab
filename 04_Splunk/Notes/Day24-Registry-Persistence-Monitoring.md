# Registry Persistence Monitoring

## Purpose

Registry monitoring helps detect persistence techniques where attackers modify Windows Registry Run Keys to execute programs automatically after user logon.

## Sysmon Event

Event ID 13 – Registry Value Set

## Important Fields

* Image
* TargetObject
* Details
* User

## SOC Investigation Focus

* Run Key modifications
* Unexpected registry changes
* PowerShell modifying registry
* Unknown executables configured for startup
* Persistence mechanisms
