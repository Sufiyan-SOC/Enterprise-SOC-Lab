# File Creation Monitoring

## Purpose

File creation monitoring provides visibility into files created by Windows processes. This helps analysts detect malware payloads, dropped executables, suspicious scripts, and unauthorized files.

## Sysmon Event

Event ID 11 – File Create

## Important Fields

* Image
* TargetFilename
* User

## SOC Investigation Focus

* Executables created in Temp or Public folders
* PowerShell-created files
* Suspicious script files
* Unexpected file locations
* Payload drop activity
