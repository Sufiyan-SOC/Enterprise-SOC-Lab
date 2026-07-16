# DNS Query Monitoring

## Purpose

DNS query monitoring helps identify which Windows processes resolve domain names before establishing network communication. Monitoring DNS activity is useful for detecting malware communication, phishing infrastructure, and suspicious outbound requests.

## Sysmon Event

Event ID 22 – DNS Query

## Important Fields

* Image
* QueryName
* QueryResults
* User

## SOC Investigation Focus

* Unknown domains
* PowerShell DNS requests
* Repeated DNS lookups
* Suspicious process activity
* Unusual DNS resolution patterns
