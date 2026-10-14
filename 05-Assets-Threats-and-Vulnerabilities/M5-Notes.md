# 📚 Introduction to Asset Security

## 🛡️ Risk, Threat, and Vulnerability Management in Cybersecurity

In cybersecurity, everyday terms take on precise technical definitions essential for incident response and defensive planning.

### 📌 Core Definitions

* **Risk:** Anything that can impact the confidentiality, integrity, or availability of an organizational asset.
* **Threat:** Any circumstance or event with the potential to negatively impact assets.
* **Vulnerability:** A weakness or flaw that can be exploited by a threat to cause harm.

### 🧮 Risk Equation and Management

Risk is not absolute and varies depending on the criticality of each organization's assets. Risk assessment relies on the fundamental formula:

$$
\text{Risk} = \text{Likelihood} \times \text{Impact}
$$

* **Analyst Focus:** Although impact depends on the business context, a security team's daily work focuses on managing and reducing the **likelihood** of occurrence.
* **Key Objectives:** Prevent costly incidents, prioritize critical assets, optimize systems, and define risk tolerance.

### 🔍 Risk Factors: Threats vs. Vulnerabilities

Risk materializes when a threat successfully exploits an existing vulnerability.

#### 1. Categories of Threats

* **Intentional:** Deliberate actions by malicious actors (e.g., an attacker exploiting a misconfigured application).
* **Unintentional:** Accidental events or human errors (e.g., an employee inadvertently granting unauthorized access to a restricted area).

#### 2. Categories of Vulnerabilities

* **Technical:** Hardware, software flaws, or incorrect system configurations.
* **Human:** Behavioral gaps or user lack of awareness (e.g., lost access cards or compromised credentials).

## 📦 Asset Classification and Security Requirements

### 📌 The Importance of Asset Management

* **Core Concept:** Asset management involves tracking assets and the risks that affect them, built on the principle that you can only protect what you know you have.
* **Types of Protected Assets:**
  * **Digital Assets:** Customer data, financial records, and databases.
  * **Information Systems:** Networks, software, and systems that process data.
  * **Physical Assets:** Facilities, equipment, and supplies.
  * **Intangible Assets:** Brand reputation and intellectual property.

### 🏷️ Common Asset Classification Levels

Asset classification labels assets based on their sensitivity and importance to an organization, helping prioritize security resources, reduce IT costs, and ensure legal compliance.

| Classification Level    | Description and Impact                                                       |
| :---------------------- | :--------------------------------------------------------------------------- |
| **Restricted**    | Highest level of sensitivity, reserved for need-to-know information.         |
| **Confidential**  | Disclosure may lead to a significant negative impact on the organization.    |
| **Internal-only** | Assets available to employees and authorized business partners.              |
| **Public**        | Lowest level; release carries no negative consequences for the organization. |

*Note:* Government and public sector organizations often label their most sensitive assets as "Confidential" rather than "Restricted".

### 🧩 Challenges in Classifying Information

* **Determining Ownership:** Identifying asset owners can be tricky, especially when company-issued laptops hold both corporate data and personal user files.
* **Overlapping Classification Levels:** Information can hold multiple sensitivity levels simultaneously (e.g., a person's name is public, but their street address is confidential).

---

## ☁️ The Emergence of Cloud Security

* **Definition:** The UK National Cyber Security Centre defines cloud computing as an on-demand, massively scalable service hosted on shared infrastructure and accessible via the internet.
* **Impact:** Modern cloud technology has lowered barriers to entry for digital businesses, enabling rapid scaling, flexibility, and cost reduction compared to traditional on-premises setups.

### 🛠️ Categories of Cloud-Based Services

Cloud services operate across three primary service models, transferring varying degrees of management responsibility between client and provider:

| Service Model                                | Description                                                                                                     | Primary Use Case / Examples                     |
| :------------------------------------------- | :-------------------------------------------------------------------------------------------------------------- | :---------------------------------------------- |
| **Software as a Service (SaaS)**       | Front-end applications hosted and fully managed by the provider; accessible via web browser.                    | Gmail, Slack, Zoom                              |
| **Platform as a Service (PaaS)**       | Online development environments and back-end tools allowing developers to write, build, and deploy custom apps. | Google App Engine, Heroku, VMware Cloud Foundry |
| **Infrastructure as a Service (IaaS)** | Remote, on-demand access to virtualized computing hardware, storage, processing, and networking.                | Google Cloud Platform, Microsoft Azure          |

### 🤝 The Shared Responsibility Model

Moving to the cloud shifts traditional security boundaries from single internal teams to a shared security framework between provider and customer:

* **Cloud Service Provider (CSP):** Secures underlying infrastructure, physical hardware, core hypervisors, and data centers.
* **Customer / Client:** Responsible for securing elements directly within their operational control:
  * **Identity & Access Management (IAM)**
  * **Resource Configurations**
  * **Data Governance & Handling**
* *Note:* The exact distribution of responsibility varies depending on whether SaaS, PaaS, or IaaS is deployed.

### ⚠️ Key Cloud Security Challenges

* **Misconfiguration:** The single largest operational vulnerability; default or poorly implemented settings leave exposed access points.
* **Cloud-Native Breaches:** Attacks specifically targeting poorly configured cloud services or exposed storage buckets.
* **Visibility & Access Monitoring:** Tracking real-time usage and access rights can be complex across multi-tenant environments.
* **Regulatory Compliance:** Ensuring data storage and transmission comply with legal and industry frameworks (e.g., HIPAA, PCI DSS, GDPR).

---

## 🏛️ NIST Cybersecurity Framework (CSF) Implementation

* **Background:** Originally released in 2014 by the National Institute of Standards and Technology (NIST) to safeguard U.S. critical infrastructure.
* **Scope:** Adapted for public and private organizations of all sizes, providing an unbiased, flexible, and scalable resource for entities lacking dedicated risk framework development resources.
* **Nature:** A voluntary framework comprising standards, guidelines, and best practices to manage cybersecurity risk and support regulatory compliance.

### 🧩 The Three Core Components

The NIST CSF consists of three primary, interconnected components designed to improve organizational security posture:

| Component          | Description                                                                                                                                                                        | Operational Role                                                                                                                    |
| :----------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------- |
| **Core**     | Desired cybersecurity outcomes organized across six functions:**Identify**, **Protect**, **Detect**, **Respond**, **Recover**, and **Govern**. | Serves as an informative reference to categorize assets, establish safeguards, detect threats, and execute response/recovery plans. |
| **Tiers**    | Measured on a scale from **1 to 4** (Tier 1 being the lowest level of implementation maturity).                                                                             | Evaluates program sophistication, assesses security posture, and identifies areas for control improvements.                         |
| **Profiles** | Expert-designed templates tailored to specific risk profiles, industries, or organizational needs.                                                                                 | Establishes operational baselines and enables comparison between current posture and target industry standards.                     |

*Note:* The **Govern** function was added to the Core in February 2024 to emphasize the role of executive leadership and decision-making in risk management.

### ⚙️ CISA Implementation Process

Implementing the CSF can be complex due to its depth. The U.S. Cybersecurity and Infrastructure Security Agency (CISA) recommends a structured four-step lifecycle:

1. **Create a Profile:** Develop a current-state operational profile outlining specific business requirements.
2. **Perform Risk Assessments:** Identify operational gaps against business and regulatory compliance standards.
3. **Analyze and Prioritize Gaps:** Evaluate security deficiencies based on current threat, risk, and vulnerability trends.
4. **Execute Action Plan:** Implement targeted mitigation plans to achieve target-state security objectives
