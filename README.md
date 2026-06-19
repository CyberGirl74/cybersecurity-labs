# Cybersecurity-Labs
Documenting my cybersecurity journey through hands-on Sysmon labs, event analysis, threat hunting, and blue-team investigations. 🌩️⚡

# Sysmon Threat Hunting Lab

## Overview

This project documents my hands-on experience installing, configuring, and investigating Windows endpoint activity using Sysmon. The goal of this lab was to gain practical experience with security monitoring, event analysis, and threat hunting techniques used by SOC Analysts and Blue Team professionals.

## Objectives

* Install and configure Sysmon
* Analyze Windows event logs
* Monitor process creation and termination events
* Investigate DNS query activity
* Practice PowerShell log analysis
* Develop threat-hunting skills

## Technologies Used

* Sysmon
* PowerShell
* Windows Event Viewer
* Windows 11
* Splunk (Installed on Host)

## Key Event IDs Investigated

| Event ID | Description                   |
| -------- | ----------------------------- |
| 1        | Process Creation              |
| 5        | Process Termination           |
| 11       | File Creation                 |
| 12       | Registry Object Create/Delete |
| 13       | Registry Value Set            |
| 22       | DNS Query                     |

## Lab Activities

### Process Creation Monitoring

Verified Sysmon Event ID 1 by launching Notepad and analyzing:

* Process Name
* Parent Process
* User Account
* Command Line
* File Hashes
* Integrity Level

### DNS Query Monitoring

Verified Sysmon Event ID 22 by generating DNS activity using:

* ping google.com
* nslookup google.com

Analyzed:

* Query Name
* Process Responsible
* User Context
* Timestamp

### PowerShell Log Analysis

Used PowerShell to query and filter Sysmon logs:

```powershell
Get-WinEvent -LogName "Microsoft-Windows-Sysmon/Operational"
```

```powershell
Where-Object {$_.Id -eq 1}
```

```powershell
Where-Object {$_.Id -eq 22}
```

## Skills Developed

* Threat Hunting
* Event Log Analysis
* Endpoint Monitoring
* PowerShell Fundamentals
* Incident Investigation
* Blue Team Operations
* Security Monitoring

## Key Takeaways

This lab provided hands-on experience with endpoint visibility and demonstrated how security analysts identify process execution, investigate DNS activity, and correlate events using Sysmon telemetry. Through this exercise, I gained practical exposure to the investigative mindset used in Security Operations Centers (SOC).

## Future Enhancements

* Integrate Sysmon with Wazuh
* Create custom detection rules
* Investigate network connection events
* Build Splunk dashboards
* Develop additional threat-hunting scenarios

---

**Author:** Shauna "Storm" Davis
**Program:** Cyber & Data Security Technology
**Focus Areas:** SOC Analyst | Threat Hunting | Blue Team Operations

