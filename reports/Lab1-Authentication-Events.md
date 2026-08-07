# Lab01-Windows-Authentication-Event-Analysis.md

## Objective

To analyze Windows Security Event Logs and understand how authentication-related activities are recorded in Event Viewer.

---

## Environment

- Operating System: Windows 10
- Tool: Windows Event Viewer
- Log Source: Windows Logs → Security

---

## Event IDs Analyzed

| Event ID | Description | Severity |
|----------|-------------|----------|
| 4624 | Successful Logon | Informational |
| 4625 | Failed Logon | Medium |
| 4672 | Special Privileges Assigned | High |
| 4688 | Process Creation | Medium |
| 4720 | User Account Created | High |
| 4732 | User Added to Privileged Group | High |

---

## Event Analysis

### Event ID 4624

**Description**

Successful user authentication.

**SOC Importance**

- Normal user login
- Used to verify user activity
- Detect unusual login timings

**MITRE ATT&CK**

- Valid Accounts (T1078)

---

### Event ID 4625

**Description**

Failed login attempt.

**SOC Importance**

- Password guessing
- Brute force attacks
- Credential attacks

**MITRE ATT&CK**

- Brute Force (T1110)

---

### Event ID 4672

**Description**

Special privileges assigned to a logon session.

**SOC Importance**

- Administrator login
- Privileged account monitoring
- Detect privilege abuse

**MITRE ATT&CK**

- Privilege Escalation

---

### Event ID 4688

**Description**

New process created.

**SOC Importance**

- Detect suspicious processes
- PowerShell execution
- CMD execution
- Malware execution

**MITRE ATT&CK**

- Command and Scripting Interpreter (T1059)

---

### Event ID 4720

**Description**

New local user account created.

**SOC Importance**

- Detect unauthorized account creation
- Persistence

**MITRE ATT&CK**

- Create Account (T1136)

---

### Event ID 4732

**Description**

User added to privileged group.

**SOC Importance**

- Privilege Escalation
- Administrator group monitoring

**MITRE ATT&CK**

- Account Manipulation (T1098)

---

## Conclusion

This lab demonstrates how Windows Security Event Logs can be used to identify authentication activities, privilege changes, account creation, and process execution. These Event IDs are commonly monitored by SOC analysts during incident investigations.
