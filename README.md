🎯 Project Goal

The goal of this project was to simulate a real-world security assessment of a museum CCTV surveillance system, focusing on business logic weaknesses, OSINT-driven credential discovery, and authentication flaws rather than brute-force or automated exploitation.

The project demonstrates how critical physical security systems can be compromised through misconfiguration, weak credentials, and missing server-side validation.

🏗️ Project Scope

Platform: TryHackMe

Environment: Simulated museum surveillance infrastructure

Assessment Focus:

Authentication mechanisms

Authorization and state management

Incident review workflows

Techniques Used:

OSINT-based credential discovery

Default credential analysis

Business logic testing

Tools:

Web browser

Source code inspection

Publicly available security reports

🔍 Initial System Reconnaissance

Upon accessing the system, an incident monitoring and reporting interface was presented instead of a traditional login page.
This suggested a workflow-driven application, where access to different system components depends on backend state rather than direct navigation.

Frontend behavior was analyzed to understand how the application communicates with backend services and manages progression between operational phases.

🚨 Business Logic Vulnerability Identified

A critical authorization and logic flaw was identified during backend interaction analysis.

A server endpoint responsible for confirming successful incident handling could be accessed directly without validating whether the required steps were completed. This allowed the application state to advance without proper authorization checks.

Security Impact:

Workflow bypass

Missing server-side validation

Excessive trust in client-side logic

This reflects a common real-world issue where business logic is enforced only at the UI level.

🔐 Credential Discovery via OSINT

After progressing to the surveillance access phase, a CCTV login portal became available.

The scenario explicitly indicated that valid credentials were based on publicly reported security audits, pointing to an OSINT-based approach rather than technical exploitation.

Public sources referenced:

Weak password policies

Default credentials in surveillance systems

Passwords derived from organization or vendor names

Commonly mentioned values included:

Louvre

Thales

🧠 Authentication Logic Analysis

Based on characteristics typical of legacy CCTV systems:

No user self-registration

No password recovery

No granular user management

It was assessed that:

Default credentials were in use

Username and password could be identical

Backend authentication might be case-sensitive

Successful Authentication:
Username: louvre
Password: louvre


This confirmed default credential exposure, representing a critical weakness in a system responsible for physical security.

🎥 Incident Footage Review & Logic Exploitation

After authentication, access to a CCTV monitoring dashboard was granted.
Initially, the system displayed only current or live footage, with no visible indicators of compromise.

However, the system’s stated objective required reviewing footage from the day of the incident, implying that sensitive data was conditionally revealed based on user input.

Action Taken:

The date filter was manually set to the incident date:

19-10-2025

Result:

Multiple camera zones entered an ALERT state

Incident-related data became visible

The following flag was revealed:

THM{cctv_4ud1ts_4r3_fun}

⚠️ Security Issues Identified
Category	Issue	Risk Level
Authentication	Default credentials	Critical
Authorization	Missing backend validation	High
Business Logic	State manipulation via logic flaws	High
Monitoring	Incident data protected only by UI logic	Medium
🧾 Final Outcome

Completed a full simulated CCTV security audit

Identified multiple high-impact, non-technical vulnerabilities

Demonstrated practical use of:

OSINT

Business logic analysis

Real-world security assessment methodology

🔑 Key Takeaways

Critical systems often fail due to logic and configuration issues, not advanced exploits

OSINT can be sufficient to compromise poorly secured environments

Physical security infrastructure frequently lacks adequate cybersecurity controls

Understanding system intent and workflow is essential for identifying real vulnerabilities

💼 Professional Relevance

This project closely mirrors real internal security assessments performed against legacy surveillance systems in public institutions, highlighting the importance of combining technical knowledge with analytical reasoning and contextual awareness.
