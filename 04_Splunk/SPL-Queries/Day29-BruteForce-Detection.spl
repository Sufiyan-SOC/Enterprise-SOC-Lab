############################################################
# Enterprise SOC Lab
# Day 29
# SMB Brute Force Detection
############################################################


############################################################
# 1. Failed Authentication Statistics
############################################################

index=* source="WinEventLog:Security" EventCode=4625
| stats count by Account_Name
| sort - count


############################################################
# 2. Successful Authentication Statistics
############################################################

index=* source="WinEventLog:Security" EventCode=4624
| stats count by Account_Name
| sort - count


############################################################
# 3. Brute Force Detection
############################################################

index=* source="WinEventLog:Security" EventCode=4625
| stats count as FailedAttempts values(Source_Network_Address) as SourceIP by Account_Name
| where FailedAttempts>=3
| sort - FailedAttempts


############################################################
# 4. Failed Login Trend
############################################################

index=* source="WinEventLog:Security" EventCode=4625
| timechart span=5m count


############################################################
# 5. Successful Login Trend
############################################################

index=* source="WinEventLog:Security" EventCode=4624
| timechart span=5m count


############################################################
# 6. Top Target Accounts
############################################################

index=* source="WinEventLog:Security" EventCode=4625
| top limit=10 Account_Name


############################################################
# 7. Top Source IP Addresses
############################################################

index=* source="WinEventLog:Security" EventCode=4625
| search Source_Network_Address!="-"
| top limit=10 Source_Network_Address


############################################################
# 8. Recent Failed Authentication Events
############################################################

index=* source="WinEventLog:Security" EventCode=4625
| table _time Source_Network_Address Account_Name FailureReason
| sort - _time
| head 20


############################################################
# 9. Authentication Investigation Timeline
############################################################

index=* source="WinEventLog:Security" (EventCode=4624 OR EventCode=4625)
| search Account_Name="aabrev"
| table _time EventCode Source_Network_Address Account_Name ComputerName
| sort _time


############################################################
# 10. Failed Authentication Count
############################################################

index=* source="WinEventLog:Security" EventCode=4625
| search Account_Name="aabrev"
| stats count as FailedAttempts by Source_Network_Address Account_Name


############################################################
# 11. Successful Authentication Validation
############################################################

index=* source="WinEventLog:Security" EventCode=4624
| search Account_Name="aabrev"
| table _time Account_Name Source_Network_Address LogonType
