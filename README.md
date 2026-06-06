# Wazuh SIEM SOC Lab

![Active Agents](screenshots/02-Wazuh-Dashboard-Active-Agents.png)

Security Operations Center (SOC) lab built using Wazuh SIEM, Windows Server Active Directory, and Windows endpoints to simulate real-world threat detection, log analysis, and incident response investigations.
Wazuh-SIEM-SOC-Lab

Security Operations Center (SOC) lab built using Wazuh SIEM, Windows Server Active Directory, and Windows endpoints to simulate real-world threat detection, log analysis, and incident response investigations.

Project Overview

This lab demonstrates the deployment and operation of a Security Information and Event Management (SIEM) platform using Wazuh.

The environment includes:

Wazuh Manager (Ubuntu Server)
Windows Server 2025 Domain Controller (DC01)
Windows 11 Endpoint (CLIENT01)
Active Directory Domain Services
Endpoint Monitoring
Threat Hunting
Security Event Correlation
Incident Investigation
MITRE ATT&CK Mapping

The objective of this project was to build a functional SOC environment capable of detecting, monitoring, and investigating Windows security events.

---

Lab Architecture
                    ┌──────────────────────┐
                    │   Wazuh Manager      │
                    │ Ubuntu Server        │
                    │ 192.168.56.101       │
                    └──────────┬───────────┘
                               │
                ┌──────────────┴──────────────┐
                │                             │
                │                             │
      ┌─────────▼─────────┐       ┌──────────▼─────────┐
      │      DC01         │       │     CLIENT01       │
      │ Windows Server    │       │ Windows 11 Pro     │
      │ Active Directory  │       │ Endpoint Agent     │
      └───────────────────┘       └────────────────────┘

---

Technologies Used
Technology	Purpose
Wazuh SIEM	Security Monitoring
Ubuntu Server	Wazuh Manager
Windows Server 2025	Domain Controller
Active Directory	Identity Management
Windows 11	Endpoint Monitoring
VirtualBox	Virtualization
MITRE ATT&CK	Threat Mapping
PowerShell	Administration
Event Viewer	Log Generation
GitHub	Documentation
Environment Deployment
Initial Wazuh Deployment

Before agent enrollment, the Wazuh dashboard showed no registered endpoints.

Successful Agent Enrollment

Both endpoints were successfully connected to the Wazuh Manager.

Connected Assets
DC01
CLIENT01

Endpoint Monitoring
Endpoint Overview

The environment contains two actively monitored Windows systems.

CLIENT01 Endpoint

Windows 11 endpoint connected to Wazuh Manager.

DC01 Domain Controller

Windows Server 2025 Domain Controller monitored through Wazuh.

Threat Hunting Dashboard

The Threat Hunting dashboard provides centralized visibility into:

Authentication events
Account management activity
Security alerts
MITRE ATT&CK techniques
Endpoint telemetry

Security Investigations

The following investigations were conducted to validate Wazuh's detection capabilities.

Investigation 1 – Failed Authentication Attempts
Detection

Wazuh detected failed logon attempts against the monitored endpoint.

Alert Information
Field	Value
Rule ID	60122
Severity	5
Event	Logon Failure
MITRE ATT&CK	T1110 – Brute Force
Findings

Multiple failed authentication attempts were generated and successfully logged by Wazuh.

Investigation 2 – User Account Creation
Detection

A new Windows account was created and detected by Wazuh.

Alert Information
Field	Value
Rule ID	60109
Severity	8
Event	User Account Created
Findings

Wazuh successfully detected and logged account creation activity on the Domain Controller.

Investigation 3 – User Account Deletion
Detection

A user account was removed from the environment.

Alert Information
Field	Value
Rule ID	60111
Severity	8
Event	User Account Deleted
Findings

The account deletion event was successfully detected and correlated by Wazuh.

Investigation 4 – Account Lockout
Detection

Repeated authentication failures triggered an account lockout.

Alert Information
Field	Value
Rule ID	60115
Severity	9
Event	Account Lockout
MITRE ATT&CK	T1110 – Brute Force
Findings

The account lockout policy generated a security alert after multiple failed login attempts.

Investigation 5 – Domain Admin Group Modification
Detection

A privileged Active Directory group was modified.

Alert Information
Field	Value
Rule ID	60159
Severity	12
Event	Domain Admins Group Changed
MITRE ATT&CK	T1098 Account Manipulation
Findings

Wazuh successfully detected modification of the Domain Admins group, a high-risk administrative action requiring investigation.

Security Impact

Changes to Domain Admin membership can indicate:

Privilege escalation
Insider threat activity
Unauthorized administrative access
Persistence mechanisms

This represented the highest-severity event generated during the lab.

Incident Reports

Detailed SOC-style incident reports were created during the investigation process.

Available Reports
Domain Admins Group Change Investigation
incident-reports/
└── INC-2026-001-Domain-Admins-Group-Change.pdf
Account Lockout Investigation
incident-reports/
└── INC-2026-002-Account-Lockout.pdf
Failed Logon Investigation
incident-reports/
└── INC-2026-003-Failed-Logon.pdf
Skills Demonstrated
SIEM Operations
Wazuh Deployment
Agent Enrollment
Log Collection
Security Monitoring
Threat Hunting
Event Correlation
Authentication Monitoring
User Behavior Analysis
Security Investigation
Windows Security
Active Directory Monitoring
Account Management Monitoring
Privileged Group Monitoring
Logon Event Analysis
Incident Response
Alert Triage
Event Investigation
Incident Documentation
Root Cause Analysis
Frameworks
MITRE ATT&CK
SOC Analyst Methodology
Incident Response Lifecycle
Project Outcomes

Successfully deployed a functional SIEM environment capable of:

Monitoring Windows endpoints
Collecting security telemetry
Detecting authentication failures
Monitoring account creation and deletion
Detecting account lockouts
Identifying privileged group modifications
Supporting SOC-style investigations
Producing formal incident reports
Author

Brandon J. Cooper

Cybersecurity | SOC Analyst | IT Support | Security Operations

GitHub Portfolio Project – Wazuh SIEM SOC Lab
