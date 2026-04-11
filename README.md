# Windows Threat Hunting Lab Using Sysmon

##  Project Overview
This project demonstrates hands-on Windows threat hunting using Sysmon to detect suspicious endpoint activity and persistence techniques. The lab simulates attacker behavior and analyzes logs to identify abnormal execution patterns and registry-based persistence.

---

##  Tools & Technologies
- Sysmon
- Windows Event Viewer
- PowerShell
- Windows 10
- Oracle VirtualBox

---

##  Threat Simulation
The following attacker-like activities were simulated:

- Suspicious execution using PowerShell
- Registry-based persistence using Run keys

---

##  Detection & Analysis

###  Event ID 1 – Suspicious Execution
Detected abnormal parent-child process relationship:

- Parent Process: `powershell.exe`
- Child Process: `notepad.exe`

This is suspicious because normally `notepad.exe` is launched by `explorer.exe`.

---

###  Event ID 13 – Registry Persistence
Detected registry modification:

- Path: `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`

This indicates a persistence mechanism used to maintain access.

---

##  Attack Chain Correlation
The activity was correlated into the following attack chain:

Execution → Persistence  
PowerShell → Registry Run Key

---

##  Incident Response
- Verified activity as controlled simulation  
- Removed persistence entry  
- Restored system to clean state  

---

##  Skills Demonstrated
- Threat Hunting  
- Sysmon Log Analysis  
- Windows Event Log Analysis  
- Process Creation Analysis  
- Registry Persistence Detection  
- Attack Chain Correlation  
- SOC Investigation  

---

##  Project Structure
