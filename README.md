#  Windows Event Log Analysis

![Windows](https://img.shields.io/badge/Platform-Windows-blue)
![SOC](https://img.shields.io/badge/Domain-SOC%20Analysis-red)
![Security](https://img.shields.io/badge/Security-Event%20Logs-green)
![MITRE](https://img.shields.io/badge/MITRE-ATT%26CK-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

# Windows Event Log Analysis

##  Project Overview

This project demonstrates Windows Security Event Log analysis using Event Viewer.

The objective is to understand how SOC Analysts investigate authentication events, privilege escalation, and process creation activities using Windows Security Logs.

---

##  Objectives

- Analyze Windows Security Logs
- Identify important Security Event IDs
- Understand authentication events
- Investigate failed logon attempts
- Monitor privileged logons
- Analyze process creation events
- Practice basic incident investigation

---

##  Lab Environment

- Windows 11
- Event Viewer
- Windows Security Logs
- GitHub

---

##  Event IDs Covered

| Event ID | Description |
|----------|-------------|
|4624|Successful Logon|
|4625|Failed Logon|
|4672|Special Privileges Assigned|
|4688|Process Creation|
|4732|User Added to Local Security Group|

---

#  Event ID 4624 – Successful Logon

### Description

Generated whenever a user successfully authenticates to Windows.

### SOC Use Case

- Verify legitimate user logins
- Detect unusual login times
- Identify lateral movement
- Investigate suspicious logins

![4624 Event List](screenshots/4624_event_list.png)

![4624 General](screenshots/4624_general.png)

---

#  Event ID 4625 – Failed Logon

### Description

Generated whenever a login attempt fails.

### SOC Use Case

- Detect brute-force attacks
- Identify password spraying
- Monitor unauthorized access attempts

![4625 Event List](screenshots/4625_event_list.png)

![4625 General](screenshots/4625_general.png)

---

#  Event ID 4672 – Special Logon

### Description

Generated when privileged accounts receive administrator-level privileges.

### SOC Use Case

- Detect privileged account usage
- Investigate privilege escalation
- Monitor administrator activity

![4672 Event List](screenshots/4672_event_list.png)

![4672 General](screenshots/4672_general.png)

---

#  Event ID 4688 – Process Creation

### Description

Generated whenever a new process starts.

### SOC Use Case

- Malware detection
- PowerShell monitoring
- Command execution monitoring
- Threat hunting

![4688 Event List](screenshots/4688_event_list.png)

![4688 General](screenshots/4688_general.png)

---

#  Event ID 4732 – User Added to Local Group

### Description

Generated when a user is added to a local security-enabled group.

### SOC Use Case

- Detect privilege escalation
- Monitor administrative group changes
- Identify unauthorized account modifications

![4732 Event List](screenshots/4732_event_list.png)

![4732 General](screenshots/4732_general.png)

---

##  Skills Demonstrated

- Windows Event Viewer
- Windows Security Logs
- Log Analysis
- Event ID Investigation
- Authentication Monitoring
- Incident Investigation
- Windows Security
- Basic Threat Hunting

---

##  References

- Microsoft Event Documentation
- MITRE ATT&CK Framework
