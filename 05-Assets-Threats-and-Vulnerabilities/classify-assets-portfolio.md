
# Home Network Asset Inventory & Risk Classification

## Activity Overview

Asset management is a critical component of an organization's security plan. It is the process of tracking assets and evaluating the risks that affect them. Effective asset management begins with creating an asset inventory—a catalog of devices that require protection—and classifying those assets based on their importance, sensitivity, and exposure to potential security risks.

This document presents a structured home office network asset inventory, completing the identification, evaluation, and classification of connected devices according to security controls and data sensitivity levels.

---

## Home Network Asset Inventory Matrix

| Asset                                    | Network access | Owner                           | Location            | Notes                                                                                                                                                 | Sensitivity   |
| :--------------------------------------- | :------------- | :------------------------------ | :------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------- | :------------ |
| **Network router**                 | Continuous     | Internet service provider (ISP) | On-premises         | Has a 2.4 GHz and 5 GHz connection. All devices on the home network connect to the 5 GHz frequency.                                                   | Confidential  |
| **Desktop**                        | Occasional     | Homeowner                       | On-premises         | Contains private information, like photos.                                                                                                            | Restricted    |
| **Guest smartphone**               | Occasional     | Friend                          | On and Off-premises | Connects to my home network.                                                                                                                          | Internal-only |
| **Work laptop**                    | Continuous     | Homeowner                       | On and Off-premises | Used for business operations, client communications, and database administration. Equipped with full-disk encryption and multi-factor authentication. | Restricted    |
| **Smart TV**                       | Continuous     | Homeowner                       | On-premises         | Used for streaming video content. Receives periodic software updates over Wi-Fi and has limited storage capacity.                                     | Internal-only |
| **Network-Attached Storage (NAS)** | Continuous     | Homeowner                       | On-premises         | Stores central file backups, financial records, and archived project documents. Access requires local authentication credentials.                     | Restricted    |

## Sensitivity Classification Framework Reference

Assets are classified using the following organizational sensitivity tiers:

| Categories              | Access Designation        | Description / Criteria                                                                                                    |
| :---------------------- | :------------------------ | :------------------------------------------------------------------------------------------------------------------------ |
| **Restricted**    | Need-to-know              | Highly sensitive assets containing confidential business or personal data. Unauthorized access causes significant impact. |
| **Confidential**  | Limited to specific users | Critical infrastructure or system components requiring administrative access controls.                                    |
| **Internal-only** | Users on-premises         | Internal devices and peripherals accessible to authorized network members or guests on-site.                              |
| **Public**        | Anyone                    | Publicly accessible resources with no sensitivity restrictions.                                                           |

## Asset Analysis & Security Evaluation

1. **Work Laptop (Restricted):**

   - **Risk Profile:** As a primary device for handling business tasks and financial/client records, compromise could lead to data breach or credential leakage.
   - **Protection Strategy:** Requires *Restricted* classification, enforcing strong password policies, full-disk encryption, and strict access controls.
2. **Network-Attached Storage (NAS) (Restricted):**

   - **Risk Profile:** Centralized storage containing critical database backups and sensitive archives. Loss or unauthorized access impacts confidentiality and integrity.
   - **Protection Strategy:** Classified as *Restricted*, limiting network exposure and requiring encrypted local connections.
3. **Smart TV (Internal-only):**

   - **Risk Profile:** Media streaming endpoint with minimal stored sensitive data. While low risk directly, compromised IoT devices can serve as network entry points.
   - **Protection Strategy:** Classified as *Internal-only* and maintained on segmented network access where possible.

## Summary

By maintaining an accurate asset inventory and mapping devices to sensitivity tiers, security practitioners can effectively scope threat exposure, prioritize patch deployment, and enforce robust defense-in-depth principles across all network endpoints.
