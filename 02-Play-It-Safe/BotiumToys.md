
# Security Audit & Compliance Assessment: Botium Toys

## Executive Summary

This document outlines a security audit performed for **Botium Toys**. The objective is to evaluate the organization's existing security posture, verify the implementation of critical security controls, and measure adherence to major compliance frameworks and auditing standards (**PCI DSS**, **GDPR**, and **SOC 1 / SOC 2**).

Based on the scope and risk assessment report, Botium Toys currently holds a high risk score of **8 out of 10**. This elevated risk is driven by unmanaged assets, unencrypted sensitive data repositories, absent intrusion detection systems, and the lack of structured disaster recovery plans.

---

## 1. Controls Assessment Checklist & Justifications

The following table evaluates whether Botium Toys currently has the necessary security controls in place, providing technical justifications based directly on the company's internal risk assessment report:

| Control                                                                       |    In Place?    | Evidence                                                                                                                                                                           |
| :---------------------------------------------------------------------------- | :-------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Least Privilege**                                                     | **❌No** | The report explicitly states that access controls pertaining to least privilege have not been implemented, as all employees currently have broad access to internally stored data. |
| **Disaster recovery plans**                                             | **❌No** | The assessment confirms that there are currently no disaster recovery plans in place to handle critical operational outages.                                                       |
| **Password policies**                                                   | ✅**Yes** | A password policy exists; however, the report notes its requirements are nominal and fall short of current minimum complexity standards.                                           |
| **Separation of duties**                                                | **❌No** | Like least privilege, separation of duties has not been established, increasing risks related to malicious insiders or compromised accounts.                                       |
| **Firewall**                                                            | **✅Yes** | The IT department successfully maintains a firewall configured to block unwanted traffic based on appropriately defined security rules.                                            |
| **Intrusion detection system (IDS)**                                    | **❌No** | The report highlights that the IT department has not yet installed or configured an IDS to monitor anomalous network traffic.                                                      |
| **Backups**                                                             | **❌No** | The company currently lacks operational backups of critical business data, severely threatening business continuity.                                                               |
| **Antivirus software**                                                  | **✅Yes** | Antivirus software is actively installed across endpoints and is monitored regularly by the IT department.                                                                         |
| **Manual monitoring, maintenance, and intervention for legacy systems** | **✅Yes** | Legacy systems are manually monitored and maintained, though the process lacks a regular schedule or clear intervention methods.                                                   |
| **Encryption**                                                          | **❌No** | Encryption is absent locally; customers' credit card information is accepted, processed, transmitted, and stored unencrypted in the local database.                                |
| **Password management system**                                          | **❌No** | There is no centralized password manager, forcing employees/vendors to manually submit IT tickets for credential resets.                                                           |
| **Locks (Offices, storefront, warehouse)**                              | **✅Yes** | Physical security is adequately maintained at the physical location via sufficient locks protecting the offices, storefront, and warehouse.                                        |
| **CCTV surveillance**                                                   | **✅Yes** | Up-to-date closed-circuit television (CCTV) surveillance systems are fully active across the physical facilities.                                                                  |
| **Fire detection/prevention**                                           | **✅Yes** | Functioning physical fire detection mechanisms (fire alarms, sprinkler systems) are properly installed.                                                                            |

---

## 2. Compliance Checklist & Regulatory Justifications

This section evaluates adherence to major regulatory standards and data protection best practices, justified by findings from the risk report:

### Payment Card Industry Data Security Standard (PCI DSS)

| Compliance Best Practice                                                |  Adhered To?  | Evidence                                                                                                                 |
| :---------------------------------------------------------------------- | :------------: | :----------------------------------------------------------------------------------------------------------------------- |
| **Only authorized users have access to credit card information.** | **❌No** | All employees have unrestricted access to internally stored data, meaning cardholder data and PII/SPII are exposed.      |
| **Credit card info is stored/processed in a secure environment.** | **❌No** | Credit card information is stored locally in an internal database without isolation or secure segmentation.              |
| **Implement data encryption procedures for transactions.**        | **❌No** | The report explicitly notes that encryption is not used to secure credit card touchpoints or local data storage.         |
| **Adopt secure password management policies.**                    | **❌No** | Password policies are nominal and lack a centralized management system to enforce strict modern complexity requirements. |

### General Data Protection Regulation (GDPR)

| Compliance Best Practice                                                      |   Adhered To?   | Detailed Justification / Evidence from Report                                                                                                   |
| :---------------------------------------------------------------------------- | :-------------: | :---------------------------------------------------------------------------------------------------------------------------------------------- |
| **E.U. customers’ data is kept private/secured.**                      | **❌No** | Privacy is compromised because least privilege access is missing and local storage lacks cryptographic protection.                              |
| **Plan in place to notify E.U. customers within 72 hours of a breach.** | **✅Yes** | Unlike other areas, the IT department has successfully established a formal plan to notify E.U. customers within 72 hours of a security breach. |
| **Ensure data is properly classified and inventoried.**                 | **❌No** | The report emphasizes that inadequate asset management forces the company to dedicate resources to properly identify and classify assets.       |
| **Enforce privacy policies and procedures.**                            | **✅Yes** | Formal privacy policies, procedures, and processes have been successfully developed and enforced among IT members and staff.                    |

### System and Organizations Controls (SOC 1, SOC 2)

| Compliance Best Practice                                                                 |   Adhered To?   | Evidence                                                                                                                           |
| :--------------------------------------------------------------------------------------- | :-------------: | :--------------------------------------------------------------------------------------------------------------------------------- |
| **User access policies are established.**                                          | **❌No** | Formal user access policies restricting privileges are absent, as separation of duties and least privilege have not been deployed. |
| **Sensitive data (PII/SPII) is confidential/private.**                             | **❌No** | Sensitive data lacks confidentiality due to generalized employee access levels and the total absence of encryption.                |
| **Data integrity ensures consistency, complete, accurate and has been validated.** | **✅Yes** | The report explicitly notes that the IT department has integrated specific controls to successfully ensure data integrity.         |
| **Data is available to authorized individuals.**                                   | **❌Yes** | The IT department maintains high system and infrastructure availability for daily business productivity.                           |

---

## 3. Strategic Recommendations for IT Management

To successfully reduce the current risk score from **8/10** to an acceptable threshold, improve the overall security posture, and satisfy legal compliance mandates, management should execute the following recommendations:

1. **Enforce Role-Based Access Control (RBAC):** Immediately implement the principle of least privilege and separation of duties to isolate sensitive financial files, PII, and cardholder data from general employees.
2. **Deploy End-to-End Encryption:** Establish cryptographic controls to protect credit card data at rest within local databases, in transit across internal networks, and at transactional touchpoints.
3. **Build Disaster Recovery & Backup Pipelines:** Create and test formal disaster recovery protocols alongside automated, regular backup routines to safeguard critical business data against permanent loss.
4. **Upgrade Identity & Access Management (IAM) and Password Controls:** Revise current nominal password policies to enforce strict modern complexity standards (minimum length, character mixing, and special characters) and implement a centralized password management solution to eliminate manual IT support ticket bottlenecks.
5. **Install Network Intrusion Detection (IDS):** Augment the existing firewall perimeter by deploying an IDS solution capable of logging and alerting on anomalous or malicious traffic patterns.
6. **Execute Comprehensive Asset Discovery:** Dedicate specific resources to identify, categorize, and document all hardware, software, and legacy systems currently under IT management.
