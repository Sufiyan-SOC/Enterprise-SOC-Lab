###############################################################
# Enterprise SOC Lab
# Use Case : Local Account & Privileged Group Discovery
# Day      : 31
# MITRE    : T1087.001, T1069.001
###############################################################


###############################################################
# 1. Detection Query
# Purpose:
# Detect execution of Windows account discovery commands.
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| table _time Computer User Image CommandLine


###############################################################
# 2. Alert Query
# Purpose:
# Trigger SIEM alert when discovery commands are executed.
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| stats count by Computer User Image CommandLine


###############################################################
# 3. Alert Triage
# Purpose:
# Quickly identify affected host and user.
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| table _time Computer User Image CommandLine ParentImage
| sort - _time


###############################################################
# 4. Investigation - Timeline
# Purpose:
# Build execution timeline for the user.
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
User="CORP\\aabrev"
| table _time Computer Image CommandLine ParentImage
| sort _time


###############################################################
# 5. Investigation - Parent Process
# Purpose:
# Identify which process launched the discovery commands.
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| stats count by ParentImage
| sort - count


###############################################################
# 6. Investigation - Frequency Analysis
# Purpose:
# Determine how often discovery commands were executed.
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| timechart span=5m count


###############################################################
# 7. Dashboard Panel - Discovery Commands
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| stats count by Image


###############################################################
# 8. Dashboard Panel - Top Users
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| stats count by User
| sort - count


###############################################################
# 9. Dashboard Panel - Activity Timeline
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| timechart span=5m count


###############################################################
# 10. Threat Hunting Query
# Purpose:
# Hunt discovery activity across all endpoints.
###############################################################

index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| stats count values(CommandLine) as Commands by Computer User
| sort - count
