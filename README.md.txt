 Windows Threat Hunting Lab Using Sysmon

>> Project Overview
This project demonstrates Windows endpoint threat hunting using Sysmon.
The objective was to detect suspicious execution and persistence techniques
by analyzing Sysmon logs in a SOC-style investigation workflow.

>> Lab Environment
- Virtualization: Oracle VirtualBox
- Guest OS: Windows 10
- Monitoring Tool: Sysmon
- Analysis Tool: Windows Event Viewer
- Scripting Tool: PowerShell

>> Tools Used
- Sysmon
- Windows Event Viewer
- PowerShell
- Registry Editor
- Oracle VirtualBox

>> Threat Simulation
The following attacker-like behaviors were safely simulated:

1. Suspicious Execution  
   PowerShell spawning Notepad, creating an abnormal parent-child
   process relationship.

2. Persistence  
   Registry Run key modification to simulate persistence commonly
   used by malware.

>>> Detection and Analysis

>> Event ID 1 – Process Creation
Sysmon Event ID 1 detected PowerShell launching Notepad.
This behavior is suspicious because Notepad is typically launched
by explorer.exe during normal user activity.

>> Event ID 13 – Registry Persistence
Sysmon Event ID 13 detected a registry value modification in:
HKCU\Software\Microsoft\Windows\CurrentVersion\Run

This confirms a persistence attempt.

>> Attack Chain Correlation
The detected activity was correlated into the following attack chain:

Execution → Persistence  
PowerShell → Registry Run Key

This sequence matches common attacker behavior patterns.

>> Incident Response
- Verified activity as controlled simulation
- Removed registry persistence entry
- Restored system to a clean state

>> Skills Demonstrated
- Windows threat hunting
- Sysmon configuration and tuning
- Log analysis using Event Viewer
- Registry analysis
- Attack chain correlation
- SOC-style documentation

>> Project Structure

Windows_Sysmon_Attack_Chain_Project
│
├── Reports
│   ├── Final_Investigation_Summary.txt
│   └── ThreatHunting_Notes_Phase3.txt
│
├── Screenshots
│   ├── 01_sysmon_custom_config.png
│   ├── 02_sysmon_installed_files.png
│   ├── 03_powershell_admin_sysmon.png
│   ├── 04_event_viewer_sysmon_operational.png
│   ├── 05_eventid1_suspicious_powershell_notepad.png
│   ├── 06_eventid13_registry_persistence.png
│   └── 07_registry_run_key_review.png
│
└── README.md


