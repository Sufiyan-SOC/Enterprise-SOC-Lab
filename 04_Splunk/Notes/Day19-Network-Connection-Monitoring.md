# Network Connection Monitoring

## Purpose

Network connection monitoring helps identify which Windows processes communicate with remote systems. It is commonly used to detect command-and-control communication, malware beaconing, and suspicious outbound connections.

## Sysmon Event

Event ID 3 – Network Connection

## Important Fields

* Image
* User
* DestinationIp
* DestinationPort
* Protocol

## SOC Investigation Focus

* Unknown destination IPs
* Uncommon destination ports
* PowerShell network activity
* Multiple outbound connections
* Suspicious process communication
