# SOC Incident Report: Apache Web Reconnaissance Detection and Automated Containment

## Incident Overview

**Incident ID:** SOC-2026-02-27-001  
**Date:** February 27, 2026  
**Analyst:** Ivan Sweeting Jr  
**Environment:** AWS EC2 (Amazon Linux 2023)  
**Severity:** Medium  
**Status:** Contained  

---

## Executive Summary

Suspicious reconnaissance activity was detected targeting the Apache web server hosted on an AWS EC2 instance. The attacker attempted to access sensitive administrative endpoints such as `/phpmyadmin`, which are commonly targeted during automated web scanning.

Fail2Ban successfully detected repeated malicious requests and automatically enforced firewall rules to block the attacker IP address.

The threat was contained without system compromise.

---

## Detection Methodology

Detection was performed using:

- Fail2Ban intrusion prevention system
- Apache access log monitoring
- firewalld automated enforcement

Log source monitored:

Fail2Ban configuration:
maxretry = 2
findtime = 300 seconds
bantime = 3600 seconds

Verification command:
sudo fail2ban-client status apache-recon


---

## Indicators of Compromise (IOCs)

| Indicator | Value |
|--------|--------|
| Source IP | 76.183.244.143 |
| Target Service | Apache HTTP Server |
| Target Port | 80 |
| Attack Type | Web Reconnaissance |
| Target Endpoint | /phpmyadmin |
| Log Source | /var/log/httpd/access_log |

---

## Timeline of Events

| Time | Event |
|-----|------|
| 23:48 | Suspicious requests detected |
| 23:49 | Fail2Ban triggered detection |
| 23:49 | Firewall rule created |
| 23:50 | Attacker IP blocked |
| 23:52 | Incident verified and contained |

---

## Containment Actions

Fail2Ban automatically executed firewall block using firewalld rich rules.

Verification command:
sudo firewall-cmd --list-rich-rules

Result:
rule family="ipv4" source address="76.183.244.143" reject


---

## Impact Assessment

No compromise occurred.

| Category | Status |
|--------|--------|
System compromise | None
Data loss | None
Service disruption | None
Threat contained | Yes

---

## Root Cause Analysis

The attacker conducted automated reconnaissance scanning for common vulnerable endpoints.

Fail2Ban successfully detected repeated access attempts and enforced automated containment.

---

## Lessons Learned

This lab demonstrated:

- Automated intrusion detection
- Log analysis skills
- Firewall automation
- Incident response workflow
- Threat containment

---

## MITRE ATT&CK Mapping

Technique:  
**T1595 – Active Scanning**

Tactic:  
**Reconnaissance**

---

## Tools Used

- AWS EC2
- Apache Web Server
- Fail2Ban
- firewalld
- Linux CLI

---

## Evidence

Evidence stored in:
04_Screenshots_and_Evidence/


Includes:

- Fail2Ban status output
- Firewall rules
- Log analysis
- Detection confirmation

---

## Conclusion

Fail2Ban successfully detected and contained reconnaissance activity. The automated security controls prevented potential exploitation and demonstrated effective defensive monitoring.

---

## Analyst

Ivan Sweeting Jr  
SOC Analyst Portfolio  
GitHub: https://github.com/ZuriZeal/Security_Portfolio
