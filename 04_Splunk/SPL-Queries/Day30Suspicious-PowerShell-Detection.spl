#######################################################
# Day 30
# Suspicious PowerShell Detection
#######################################################

#######################################################
# PowerShell Execution
#######################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
| table _time Computer User ParentImage CommandLine
| sort - _time

#######################################################
# PowerShell Trend
#######################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
| timechart span=5m count

#######################################################
# Top Users
#######################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
| top User

#######################################################
# Top Endpoints
#######################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
| top Computer

#######################################################
# Parent Process
#######################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
| top ParentImage

#######################################################
# Suspicious PowerShell
#######################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
(CommandLine="*-enc*" OR CommandLine="*-EncodedCommand*" OR CommandLine="*-nop*" OR CommandLine="*-w hidden*" OR CommandLine="*DownloadString*" OR CommandLine="*Invoke-WebRequest*")
| table _time Computer User ParentImage CommandLine
| sort - _time

#######################################################
# Investigation
#######################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
| table _time Computer User ParentImage ProcessId CommandLine
| sort - _time
