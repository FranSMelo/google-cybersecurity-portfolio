# #1 Incident Handler's Journal: Healthcare Clinic Ransomware Incident

## Overview & Context

This document represents the first professional entry in an Incident Handler's Journal, capturing the initial intake, forensic breakdown, and analytical review of a severe cybersecurity incident affecting a primary-care healthcare facility. The scenario details an organized ransomware attack delivered via targeted phishing, highlighting operational disruption and incident response documentation standards.

---

## Incident Journal Entry

* **Date:** October 20, 2026
* **Entry:** 1
* **Description:** Initial incident response journal entry documenting a ransomware attack on a U.S. healthcare clinic triggered by a targeted phishing email containing a malicious attachment.
* **Tool(s) Used:** Virtualization software (for safe artifact isolation), Endpoint Detection and Response (EDR) logs, and internal incident ticketing systems.

### The 5 W's

* **Who** caused the incident?The incident was initiated by an organized group of unethical external hackers known for targeting healthcare and transportation industries, who deployed malware via phishing emails sent to clinic employees.
* **What** happened? Employees downloaded malicious email attachments that deployed ransomware, encrypting critical medical records and files, displaying a ransom note demanding money for decryption keys, and severely shutting down business operations.
* **When** did the incident occur? The security incident occurred on a Tuesday morning at approximately 9:00 a.m.
* **Where** did the incident happen? The incident took place at a small U.S. health care clinic specializing in delivering primary-care services.
* **Why** did the incident happen? The attack succeeded because employees fell victim to targeted phishing emails and downloaded malicious attachments without adequate email filtering or endpoint security controls, allowing threat actors to compromise the network and encrypt critical files.

### Additional Notes

* **Observations & Questions:** This incident underscores how human error remains a primary vector for ransomware delivery in critical sectors like healthcare. It raises critical questions regarding the organization's email gateway security, employee cybersecurity awareness training, and whether robust offline, immutable backups were maintained to ensure business continuity without paying extortion demands.

---

## Summary

Documenting security incidents using structured frameworks like the 5 W's ensures clear communication among incident responders, stakeholders, and legal teams. This journal entry serves as a foundational reference for establishing robust email security, endpoint protection, and disaster recovery playbooks to prevent future ransomware infections.

---

---



## #2 Incident Journal Entry: Phishing

- **Date:** October 20, 2026
- **Entry:** 2
- **Description:** Phishing incident investigation and ticket escalation (Alert A-2703) targeting the HR department at `hr@inergy.com` via a malicious password-protected executable attachment (`bfsvc.exe`).
- **Tool(s) Used:** Phishing Incident Response Playbook, Email Gateway Security Logs, VirusTotal, and Internal Incident Ticketing System.

### The 5 W's

- **Who** caused the incident? The incident was initiated by external threat actors spoofing identity details via a suspicious sender address (`76tguyhh6tgftrt7tg.su`).
- **What** happened? An employee received a phishing email containing a password-protected malicious executable attachment (`bfsvc.exe`), which was downloaded and executed on the endpoint, prompting an IDS alert.
- **When** did the incident occur? The security incident took place on Wednesday, July 20, 2022, at 09:30:14 AM.
- **Where** did the incident happen? The incident occurred at the workstation assigned to `hr@inergy.com` within the corporate network.
- **Why** did the incident happen? The attack succeeded because threat actors utilized targeted social engineering (fake job application pretext), domain anomalies, and password-based payload encryption to bypass perimeter filters and deceive the end-user into executing the malware.

### Additional Notes & Playbook Execution

- **Playbook Flowchart Navigation:** `[Step 1: Receive Alert] -> [Step 2: Evaluate Alert] -> [Step 3.0: Has Attachments? YES] -> [Step 3.1: Is Attachment Malicious? YES] -> [Step 3.2: Update & Escalate]`
- **Observations & Questions:** This incident demonstrates how attackers leverage password-protected attachments to evade basic mail gateway inspections. Verification of the SHA256 file hash against threat intelligence confirmed a 44/64 detection ratio on VirusTotal (classified as a Trojan/Backdoor). Following playbook procedures, the ticket status was successfully updated to **Escalated** and handed over to Tier-2 SOC analysts for endpoint containment.

---

## Summary

Documenting recurring security incidents using structured evaluation criteria ensures compliance with organizational playbooks and smooth handoffs between different tiers of a Security Operations Center (SOC). This second journal entry reinforces the critical importance of validating file hashes and identifying social engineering red flags during phishing triage.
