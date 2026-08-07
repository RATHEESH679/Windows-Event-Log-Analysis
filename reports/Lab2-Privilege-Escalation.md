# Lab 02-Account-Management-Events.md

## Objective

To analyze Windows Security Event Logs related to privilege escalation and identify indicators of suspicious administrative activity.

---

## Environment

- Operating System: Windows 10
- Tool: Event Viewer
- Log Source: Windows Logs → Security

---

## What is Privilege Escalation?

Privilege escalation occurs when a user or process gains permissions beyond those originally assigned.

Attackers commonly attempt privilege escalation after obtaining initial access to a system to gain administrative privileges and execute sensitive actions.

---

# Event ID 4672 - Special Privileges Assigned

## Description

This event is generated whenever special administrative privileges are assigned to a new logon session.

---

## Why is it Important?

This event indicates that an account logged in with administrator-level privileges.

While normal for administrators, unexpected occurrences may indicate:

- Compromised administrator account
- Privilege abuse
- Malware running as SYSTEM
- Unauthorized administrative access

---

## Investigation Steps

Check:

- Account Name
- Logon ID
- Time Created
- Source Workstation
- Related Event ID 4624

Determine:

- Was the login expected?
- Is the account normally an administrator?
- Was the login remote?

---

## Severity

Medium

High if unexpected.

---

## MITRE ATT&CK Mapping

Technique:

T1078 – Valid Accounts

TA0004 – Privilege Escalation

---

# Event ID 4688 - Process Creation

## Description

Generated whenever a new process starts.

---

## Why is it Important?

SOC analysts use this event to identify suspicious tools such as:

- powershell.exe
- cmd.exe
- rundll32.exe
- regsvr32.exe
- mshta.exe
- wmic.exe

These binaries are commonly abused by attackers.

---

## Investigation Steps

Review:

- Process Name
- Parent Process
- Command Line
- User Account

Questions:

- Is the command expected?
- Was PowerShell launched by Office?
- Was cmd.exe started by a user?

---

## Severity

Medium

High if suspicious commands are executed.

---

## MITRE ATT&CK Mapping

T1059 – Command and Scripting Interpreter

---

# Event ID 7045

## Description

A new Windows service has been installed.

---

## Why is it Important?

Attackers frequently install malicious services for persistence.

---

## Investigation Steps

Review:

- Service Name
- Service Path
- Account
- Installation Time

Determine:

- Is the service legitimate?
- Was it installed by an approved application?

---

## Severity

High

---

## MITRE ATT&CK Mapping

T1543.003

Create or Modify System Process: Windows Service

---

# SOC Analyst Findings

| Event ID | Purpose | Severity |
|----------|----------|----------|
|4672|Administrative privileges assigned|Medium|
|4688|Process creation monitoring|Medium-High|
|7045|New service installation|High|

---

# Indicators of Suspicious Activity

- Unexpected administrator logins
- PowerShell execution
- Unknown services installed
- Suspicious parent-child processes
- Administrative activity outside business hours

---

# Conclusion

Monitoring privilege escalation events helps SOC analysts detect unauthorized administrative activity, malware execution, persistence mechanisms, and attacker behavior during post-compromise stages.

Proper investigation of Events 4672, 4688, and 7045 improves early detection and incident response capabilities.
