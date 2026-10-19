# 🛡️ Course 5: Assets, Threats, and Vulnerabilities

<p align="center">
  <img src="https://img.shields.io/badge/Google_Cybersecurity-Course_5-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Google Cybersecurity Professional Certificate — Course 5"/>
  <img src="https://img.shields.io/badge/Focus-Asset_Security_%7C_Threat_Modeling-0077B6?style=for-the-badge" alt="Focus: Asset Security and Threat Modeling"/>
</p>

## 📌 Course Overview

**Assets, Threats, and Vulnerabilities** explores how cybersecurity professionals identify and classify organizational assets, assess the risks affecting them, and select safeguards to protect them. The course develops an attacker mindset while connecting asset security to vulnerability management, access controls, data privacy, and threat modeling.

This section of my portfolio combines course notes with practical assessments and incident analyses. The exercises apply security concepts to scenarios involving a home network, a commercial bank, an exposed e-commerce database, a mobile marketplace, unauthorized payroll activity, data exposure, and USB baiting.

## 🎯 What I Learned

- **Identify and classify assets:** Build inventories of physical and digital assets and classify them according to sensitivity, importance, and access requirements.
- **Assess risk:** Analyze how threats may exploit vulnerabilities, estimate likelihood and impact, and use risk scores to prioritize remediation.
- **Protect organizational assets:** Apply least privilege, role-based access control (RBAC), authentication, authorization, encryption, and data segregation.
- **Manage data securely:** Understand data governance and the data lifecycle, from collection and storage through use, archiving, and destruction.
- **Understand privacy requirements:** Recognize the importance of protecting PII, SPII, and PHI and consider relevant requirements such as GDPR, PCI DSS, and HIPAA.
- **Assess vulnerabilities:** Examine system exposure, identify potential attack paths, and recommend controls that reduce the attack surface.
- **Model threats:** Apply structured threat modeling, including the PASTA methodology, to connect business objectives, technical components, threats, vulnerabilities, and mitigations.
- **Think like a threat actor:** Consider how social engineering, credential misuse, misconfiguration, and insecure access could put assets at risk.

## 🧪 Practical Exercises & Assessments

- Created a **home network asset inventory**, assigning sensitivity classifications and considering protection needs for connected devices.
- Developed a **commercial bank risk register**, scoring risks such as business email compromise, exposed financial records, theft, and supply chain disruption.
- Assessed an **e-commerce database exposed to the public internet**, using a NIST SP 800-30-based approach to evaluate risk and recommend network isolation, VPN access, least privilege, and monitoring.
- Applied the **PASTA threat modeling methodology** to a sneaker marketplace mobile application, mapping attack paths such as SQL injection and session hijacking to defensive controls.
- Investigated an **unauthorized payroll transaction**, identifying failures in account deprovisioning and excessive administrative privileges.
- Analyzed a **data leak scenario** and recommended time-limited access, role-based permissions, and improved activity monitoring.
- Evaluated a **USB baiting scenario**, identifying social engineering and data exposure risks and recommending user training and technical restrictions.

## 📄 Portfolio Deliverables

| Resource                                                                       | Description                                                                                                                  |
| :----------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------- |
| [Course Notes](M5-Notes.md)                                                     | Study notes covering asset security, risk, access controls, data governance, vulnerabilities, threats, and related concepts. |
| [Asset Classification](classify-assets-portfolio.md)                            | Home network asset inventory, sensitivity classifications, and security considerations.                                      |
| [Risk Register](risk-register-portfolio.md)                                     | Commercial bank risk analysis, scoring methodology, priorities, and mitigation focus.                                        |
| [Vulnerability Assessment Report](vulnerability-assessment-report-portfolio.md) | Risk assessment of an internet-exposed e-commerce database with recommended remediations.                                    |
| [PASTA Threat Model](PASTA-workesheet.md)                                       | Seven-stage threat modeling assessment for a sneaker marketplace mobile application.                                         |
| [Access Control Investigation](access-control-portfolio.md)                     | Payroll incident analysis focused on account lifecycle management and least privilege.                                       |
| [Data Leak Analysis](Data-leak-portfolio.md)                                    | Assessment of accidental external exposure and recommendations aligned with NIST SP 800-53 AC-6.                             |
| [USB Baiting Analysis](parking-usb-portfolio.md)                                | Physical social engineering risk assessment and layered mitigation recommendations.                                          |

## 🗂️ Folder Contents

```text
05-Assets-Threats-and-Vulnerabilities/
├── README.md
├── M5-Notes.md
├── classify-assets-portfolio.md
├── risk-register-portfolio.md
├── vulnerability-assessment-report-portfolio.md
├── PASTA-workesheet.md
├── access-control-portfolio.md
├── Data-leak-portfolio.md
├── parking-usb-portfolio.md
└── image/
```

## 💡 Key Takeaway

Protecting assets starts with knowing what an organization has and why it matters. By classifying assets, evaluating threats and vulnerabilities, and prioritizing risk-based controls, security teams can reduce exposure while protecting confidentiality, integrity, and availability.
