IA 462 MIDTERM 

Repository Description
This repository is a security focused lab overview. It demonstrates Linux hardening, Windows security monitoring, Docker container hardening, vulnerability assesments, policy enforcement, threat detection,
 and supply chain security controls. This midterm combines administration, security analysis, container security, threat detection, and security operations practices into a single repository.
 The objective of this repository is to demonstrate how a modern application can be secured from the operating system layer throughout the CI/CD pipeline. 







Midterm Cross‑Platform Comparison
Control Area	               Linux	                        Windows                                 	Docker (Containers)
Kernel Model	  Monolithic; everything in one kernel space	Hybrid NT kernel	           Shared host kernel; isolated namespaces/cgroups
Access Control	      DAC + MAC (SELinux/AppArmor)	     ACLs + UAC + AD-based policy	    User namespaces, capability dropping
Auditing / Logging	syslog, journald, auditd	     Event Viewer, ETW, Security Logs	         Container logs + host-level auditing
Hardening Standard	CIS Linux, SELinux, AppArmor	    CIS Windows, Defender, GPO baselines	 CIS Docker, image scanning, least-privilege users
Common Attack Surface	SSH, misconfig, weak perms	     RDP, SMB, PowerShell misuse	          Privilege escalation, breakout, bad images


For Linux, the most important hardening step I would prioritize is disabling unused services. I am referencing slide 11 Linux Hardening Essentials.
For Windows, I would prioritize disabling sbmv1 and other legacy protocols. I am referencing slide 16 Windows Hardening Best Practices.
For Docker, I would use minimal base images. I am refernecing slide 21 Docker Security.


Supply Chain Threat Model
Vulnerability 1: Open source dependencies
an attacker might exploit a vulnerable python package included in the repository
controls would be requirements.txt with exact version pinning and dependabot alerts.
I pulled this from the week 8 slideshow about dependancy management. 
Vulnerability 2: container privelege escalation
an attacker might try to gain increased access inside the docker container
controls would be to run containers as not root, have read only files, and add rules
I pulled this from the week 6 slideshow docker containers, slide 15

Learning objectives:
Section 1: Linux Host Hardening + Lynis
Demonstrates Linux best practices to protect agianst supply chain attacks
Utilizes security techniques across Linux environments
Section 2 — Windows Baseline + Event Log Analysis
Implement Windows best practices to protect against Supply Chain Attacks.
Utilize Supply Chain Security Techniques across Windows environments.
Section 3 — Docker Hardened Build + Runtime Controls
Apply enterprise patch and policy management for Docker Containers, including container hardening.
Utilize Supply Chain Security Techniques across Docker container environments.
Section 4 — Trivy + Syft + Grype Scan Report
Perform Vulnerability Management: scan, patch, and retest continuously using CI/CD techniques in GitHub.
Configure and manage third-party security scanners within a GitHub CI/CD pipeline.
Section 5 — Policy Enforcement (Docker Bench + Sigma Rule)
Apply enterprise patch and policy management for Docker Containers, including container hardening.
Utilize Supply Chain Security Techniques across Docker
Section 6 — Dependency Pinning + Dependabot + Dependency Review Gate
Apply Dependency Pinning, Version Control, and Hashing to reduce surprise supply chain attacks.




