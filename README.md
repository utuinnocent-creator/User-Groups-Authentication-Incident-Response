# User, Group, and Authentication Hardening (Incident Response)

## Overview
I conducted an incident response–style security audit and remediation on Ubuntu 22.04 using Lynis. The goal was to identify vulnerabilities in authentication, user/group management, and system hardening, then apply fixes aligned with CIS Benchmarks and organizational security policies.

## Key Findings
- Weak password aging policies
- Insecure SSH configuration (root login enabled)
- Disabled firewall protection
- Improper file permissions on sensitive files
- Outdated packages missing security updates

## Remediation Actions
- Enforced password aging (`PASS_MAX_DAYS 90`, `PASS_MIN_DAYS 7`, `PASS_WARN_AGE 14`)
- Disabled root SSH login (`PermitRootLogin no`)
- Enabled firewall with UFW and restricted unnecessary traffic
- Corrected file permissions (`chmod 640 /etc/shadow`, `chmod 644 /etc/passwd`)
- Updated packages with `apt upgrade`

## Results
- Hardening index improved from **58 → 78**
- Authentication strengthened
- SSH hardened against remote compromise
- Firewall enforced network security
- File permissions secured sensitive authentication data
- System patched against known vulnerabilities

## Remaining Recommendations
- Implement Multi-Factor Authentication (MFA)
- Deploy intrusion detection tools (AIDE, Fail2Ban, OSSEC)
- Configure centralized logging and SIEM integration
- Automate Lynis audits with cron jobs

## Reflection
This project reinforced the value of structured incident response for system hardening. It improved my skills in:
- Linux administration
- Authentication and access control
- Firewall management
- Security auditing with Lynis
- Applying CIS Benchmarks in practice

## Conclusion
By following incident response phases—preparation, detection, containment, remediation, and verification—I significantly improved system resilience and compliance posture. This project demonstrates practical DevOps and cybersecurity skills in securing authentication and user/group configurations.
