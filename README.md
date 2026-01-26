# Active-Directory-Security-Lab
Active Directory Security Monitoring Lab

Password Spraying & Privilege Escalation Detection

📌 Project Description

This project demonstrates a hands-on Blue Team / SOC monitoring lab focused on detecting and analyzing common Active Directory attack techniques using native Windows Security logs.
The lab simulates realistic attack scenarios against an Active Directory environment and documents how suspicious activity can be identified, correlated, and mitigated based on event log analysis.

The primary goal of this project is to showcase:
- Understanding of Active Directory authentication mechanisms
- Ability to detect credential-based attacks
- Log analysis and event correlation skills
- Incident reporting in a SOC-style format

Lab Environment:
Domain: LAB.LOCAL
Domain Controller: Windows Server (AD DS)
Client: Windows 10
Authentication: Kerberos
Logging: Windows Security Auditing enabled via GPO

Active Directory Structure
LAB.LOCAL
├── IT
│    ├── Admins
│    └── Workstations
├── HR
├── SOC
└── ServiceAccounts

Domain users and security groups configured to simulate a small enterprise environment
Group Policies applied for password policy, auditing, and security hardening

Simulated Attack Scenarios

**Password Spraying Attack**

A password spraying attack was simulated using built-in Windows tools to generate multiple authentication attempts across different domain user accounts using the same password.

Objective:
- Detect abnormal authentication patterns
- Identify Kerberos-based authentication failures
- Observe account lockout enforcement

Key Indicators:
- Multiple failed Kerberos authentications across different users
- Same source system
- Short time window between attempts

**Privilege Escalation via Group Membership / GPO Abuse**
A privilege escalation scenario was simulated by modifying group memberships and Group Policy links, resulting in elevated privileges on a domain-joined system.

Objective:
- Detect unauthorized privilege changes
- Identify GPO-related modifications
- Monitor local administrator group changes on endpoints

Incident Response Outcome
- Password spraying activity was detected at the authentication stage
- One account lockout occurred as a result of enforced security policy
- No successful authentication or lateral movement was observed
- Privilege escalation attempts were identified through audit logs
- Domain integrity remained intact
- Incident Reports

Detailed SOC-style incident reports with screenshots and evidence are provided in PDF format:

- Password Spraying Incident Report
- Privilege Escalation Incident Report

Available in the reports/ directory of this repository.

Skills Demonstrated
- Active Directory security fundamentals
- Windows Security log analysis
- Kerberos authentication understanding
- Event correlation and attack detection
- SOC incident reporting
- Blue Team mindset and methodology


This project is designed as a defensive security lab.
No offensive tooling or exploit development is included.
All activities were performed in an isolated lab environment for educational purposes.
