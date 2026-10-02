# 📚 Security domains

## 🛡️ The 8 CISSP Security Domains

![j1FbNS82S1yYlxE-Igbeww_15365b8830a9459285e35f2c933705f1_1oSzH-WlqUZe0MTeQnysKIvtlhXgJLES9dw5McvmUZL-EwfcEQLEDVcXErzxOnVYOJlIqqAK1mafq5Oq9C3lniHKrVvbcChb4_eChT-nusF47qadYlvZV05YzW302o7kstvEsIOw48J8Op_AsTU793sNiXroLTeq8gCo5KrOZiNiIqp6f2P0PLfdfv-BBQ (1600×933)](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/j1FbNS82S1yYlxE-Igbeww_15365b8830a9459285e35f2c933705f1_1oSzH-WlqUZe0MTeQnysKIvtlhXgJLES9dw5McvmUZL-EwfcEQLEDVcXErzxOnVYOJlIqqAK1mafq5Oq9C3lniHKrVvbcChb4_eChT-nusF47qadYlvZV05YzW302o7kstvEsIOw48J8Op_AsTU793sNiXroLTeq8gCo5KrOZiNiIqp6f2P0PLfdfv-BBQ?expiry=1791019065984&hmac=Krj0FwTnfvtUpuETK9zbgO7FeyAngf2wG1fc3MTMuVk)

**Source:** Google Cybersecurity Professional Certificate, Google/Coursera, course material. Image used for educational/reference purposes.

### 🔒 1. Security and Risk Management

* **Focus:** Developing and maintaining an organization's overall security posture and defense capabilities against changes and threats.
* **Key Elements:** Security goals, risk mitigation processes, compliance (e.g., GDPR), business continuity plans, legal regulations, and professional ethics.
* **InfoSec Processes:** Incident response, vulnerability management, application security, cloud security, and infrastructure security.

### 📦 2. Asset Security

* **Focus:** Managing cybersecurity processes for organizational assets, including storage, maintenance, retention, and destruction of physical and virtual data.
* **Key Elements:** Accurate asset/data tracking, security impact analysis, recovery plans, and data exposure management.
* **Practical Example:** Creating and managing backups to ensure environment restoration during a security incident.

### 🏗️ 3. Security Architecture and Engineering

* **Focus:** Managing data security through effective tools, systems, and processes created by security architects and engineers.
* **Key Elements:** Shared responsibility, threat modeling, least privilege, defense in depth, fail securely, separation of duties, and Zero Trust architecture.
* **Practical Example:** Using SIEM (*Security Information and Event Management*) tools to monitor for unusual login or user activity.

### 🌐 4. Communication and Network Security

* **Focus:** Managing and securing physical networks, wireless communications, and remote, hybrid, or on-site work environments.
* **Key Elements:** Network security controls (such as restricted network access) and external connection management for remote workers.
* **Objective:** Ensuring data remains secure regardless of employee locations.

### 🔑 5. Identity and Access Management (IAM)

* **Focus:** Ensuring user identities are trusted and authenticated, authorizing access only to legitimate physical and logical assets.
* **Core Principle:** Least privilege (granting only the minimal access required to complete a task).
* **Practical Example:** Granting temporary access to customer data to a support representative only while resolving an issue, then removing access afterward.

### 🔍 6. Security Assessment and Testing

* **Focus:** Proactively identifying and mitigating risks, threats, and vulnerabilities across internal systems.
* **Key Elements:** Penetration testing (*pen testers*), security control testing, data collection, audits, and user permission validation.
* **Objective:** Reducing the probability of a data breach by catching flaws before threat actors do.

### 🚨 7. Security Operations

* **Focus:** Investigating potential data breaches and implementing preventative measures after a security incident occurs.
* **Key Elements:** Training and awareness, reporting/documentation, intrusion detection and prevention, SIEM tools, log management, incident management, playbooks, post-breach forensics, and lessons learned.
* **Objective:** Managing and mitigating active attacks in real-time to protect private information.

### 💻 8. Software Development Security

* **Focus:** Applying secure programming practices and guidelines throughout the entire Software Development Life Cycle (SDLC).
* **Key Elements:** Security must be integrated from design through testing and release (never an afterthought), application testing, and quality assurance (QA).
* **Practical Example:** Ensuring proper encryption configuration for a new medical device storing private patient data.

---

## 📉 Managing Security Risks and Threats

### 🔍 Understanding Risk Management

* **Focus:** Protecting organizational assets (both digital and physical) from threats, risks, and vulnerabilities using frameworks like the NIST Risk Management Framework (RMF) and HITRUST.
* **Key Elements:**
  * **Digital Assets:** Personal identifiable information (PII) such as Social Security Numbers (SSNs), dates of birth, bank account numbers, and mailing addresses.
  * **Physical Assets:** Payment kiosks, servers, desktop computers, and office spaces.
* **Risk Management Strategies:**
  * **Acceptance:** Accepting a risk to avoid disrupting business continuity.
  * **Avoidance:** Creating a plan to avoid the risk altogether.
  * **Transference:** Transferring risk to a third party to manage.
  * **Mitigation:** Lessening the impact of a known risk.

### ⚠️ Today’s Most Common Threats, Risks, and Vulnerabilities

### 🎯 Threats

* **Definition:** Any circumstance or event that can negatively impact assets from the inside or outside.
* **Key Examples:**
  * **Insider threats:** Staff members or vendors abusing authorized access.
  * **Advanced persistent threats (APTs):** Threat actors maintaining unauthorized access to a system for an extended period.

### 📊 Risks

* **Definition:** Anything that can impact the confidentiality, integrity, or availability of an asset (Risk equals the likelihood of a threat).
* **Key Factors:**
  * **External risk:** Outside factors or threat actors attempting to gain access to private information.
  * **Internal risk:** Current or former employees, vendors, or trusted partners.
  * **Legacy systems:** Outdated or unmanaged systems (e.g., old workstations or mainframes).
  * **Multiparty risk:** Third-party vendors accessing intellectual property or trade secrets.
  * **Software compliance/licensing:** Outdated software or unapplied patches.
* **Industry Standards:** Utilizing resources like NIST guidelines and the **OWASP Top 10** standard awareness document for critical security risks to web applications.

### 🔓 Vulnerabilities

* **Definition:** A weakness that can be exploited by a threat, requiring regular inspection and vulnerability management.
* **Key Vulnerability Examples:**

  * **ProxyLogon:** A pre-authenticated vulnerability affecting Microsoft Exchange servers. This means a threat actor can complete a user authentication process to deploy malicious code from a remote location.
  * **ZeroLogon:** A vulnerability in Microsoft’s Netlogon authentication protocol. An authentication protocol is a way to verify a person's identity. Netlogon is a service that ensures a user’s identity before allowing access to a website's location.
  * **Log4Shell:** Allows attackers to run Java code on someone else’s computer or leak sensitive information. It does this by enabling a remote attacker to take control of devices connected to the internet and run malicious code.
  * **PetitPotam:** Affects Windows New Technology Local Area Network (LAN) Manager (NTLM). It is a theft technique that allows a LAN-based attacker to initiate an authentication request.
  * **Security logging and monitoring failures:** Insufficient logging and monitoring capabilities that result in attackers exploiting vulnerabilities without the organization knowing it
  * **Server-side request forgery:** Allows attackers to manipulate a server-side application into accessing and updating backend resources. It can also allow threat actors to steal data.
* **Practical Role:** Monitoring systems constantly, identifying weaknesses early, and applying patches or updates to reduce exposure.

---

---

# 📚Security Frameworks and Controls

## 📋 Frameworks and Controls Overview

* **Focus:** Using security frameworks and controls together to help mitigate organizational risk, protect data and privacy, and support regulatory compliance.
* **Security Frameworks:** Guidelines used to build risk-mitigation plans and comply with laws (e.g., complying with HIPAA in the healthcare industry)
* **Security Controls:** Safeguards designed to reduce specific security risks (e.g., using multi-factor authentication, or MFA).

### 📐 Specific Frameworks

#### 🌐 Cyber Threat Framework (CTF)

* **Definition:** Developed by the U.S. government to provide a common language for describing and communicating information about cyber threat activity.
* **Purpose:** Helps professionals analyze and share information efficiently to improve responses to evolving threat tactics and techniques.

#### 🌐 International Organization for Standardization / International Electrotechnical Commission (ISO/IEC) 27001

* **Definition:** An internationally recognized family of standards enabling organizations of all sizes to manage asset security (financial info, IP, employee data, third-party data).
* **Purpose:** Outlines information security management system (ISMS) requirements, best practices, and a collection of optional controls to improve security posture.

### ⚙️ Security Control Categories

* **Objective:** Used alongside frameworks to reduce the possibility and impact of threats, risks, and vulnerabilities through physical, technical, and administrative measures (preventing, detecting, or correcting issues).

#### 🚪 Physical Controls

* **Examples:** Gates, fences, locks, security guards, CCTV/surveillance cameras, motion detectors, and access cards/badges.

#### 💻 Technical Controls

* **Examples:** Firewalls, multi-factor authentication (MFA), and antivirus software.

#### 📄 Administrative Controls

* **Examples:** Separation of duties, authorization, and asset classification.

---

## 🔒 The CIA Triad for Cybersecurity Analysts

* **Focus:** Using the confidentiality, integrity, and availability (CIA) triad model to inform risk considerations, system design, and security policies.
* **Security Posture:** Maintaining an acceptable risk level and applying these elements helps establish an organization's defense and reaction capabilities.

### 👁️ Confidentiality

* **Definition:** Ensuring that only authorized users can access specific assets or data.
* **Key Implementation:** Utilizing design principles like the **principle of least privilege** to limit user access solely to the information required for work-related tasks.

### ✅ Integrity

* **Definition:** Ensuring that data is verifiably correct, authentic, and reliable.
* **Key Mechanisms:**
  * **Cryptography:** Transforming data so unauthorized parties cannot read or tamper with it (NIST, 2022).
  * **Encryption:** Converting readable data into an encoded format to prevent tampering (e.g., protecting messages on internal chat platforms).

### 🔓 Availability

* **Definition:** Ensuring that data remains accessible to authorized users whenever it is needed.
* **Practical Application:** Permitting remote employees to access internal corporate networks to perform their jobs, while maintaining controlled access boundaries based on specific department needs (e.g., accounting personnel accessing accounts rather than development data).

---

## 🛡️ OWASP Security Principles

**Focus:** Integrating security principles into daily analyst tasks—such as log analysis, monitoring SIEM dashboards, or using vulnerability scanners.

### 🔑 Core OWASP Principles (Review)

* **Minimize attack surface area:** Reducing all potential vulnerabilities that a threat actor could exploit.
* **Principle of least privilege:** Granting users the minimum amount of access required for their everyday tasks.
* **Defense in depth:** Implementing varying security controls to mitigate risks and threats.
* **Separation of duties:** Distributing critical actions across multiple people under the principle of least privilege.
* **Keep security simple:** Avoiding unnecessarily complex solutions that make security difficult.
* **Fix security issues correctly:** Finding root causes, containing impacts, identifying vulnerabilities, and testing remediation success.

### ➕ Additional OWASP Security Principles

#### ⚙️ Establish Secure Defaults

* **Definition:** An application's optimal security state should be its default state for users, meaning it takes extra effort to make the application insecure.

#### 🔌 Fail Securely

* **Definition:** Ensuring that when a security control fails or stops working, it defaults to the most secure option.
* **Practical Example:** A failing firewall should close all connections and block new ones rather than accept all traffic.

#### 🚫 Don’t Trust Services

* **Definition:** Organizations must not explicitly trust the security systems of third-party partners, as outside partners often have different policies.
* **Practical Example:** An airline partnering with a third-party vendor that tracks reward points should independently verify balance accuracy before sharing information with customers.

#### 🔍 Avoid Security by Obscurity

* **Definition:** Key system security should not rely purely on keeping design details or source code hidden.
* **Key Factors:** Security must rely on robust factors like reasonable password policies, defense in depth, transaction limits, solid network architecture, and fraud/audit controls.

--

## 🔍 Security Audits and Compliance

*  **Definition:** An independent review evaluating whether an organization meets internal criteria (policies, procedures, best practices) and external criteria (regulatory compliance, laws, federal regulations).

* **Purpose:** Assesses established security controls, ensures daily monitoring checks are performed, and identifies threats, risks, and vulnerabilities to maintain security posture.
* **Goals and Objectives:** Ensure IT practices meet industry standards, identify areas for remediation and growth, safeguard data, and avoid governmental fines and penalties.
* **Determining Factors:** Audit types depend on industry type, organization size, government regulations, geographical location, and voluntary compliance choices.
* **Role of Frameworks:** Frameworks like NIST CSF and ISO 27000 help organizations prepare for audits and save time during internal and external reviews.

### 📝 Audit Checklist Steps

* **1. Identify the Scope:** List assets to assess, note audit goals, set performance frequency, and evaluate policies/procedures.
* **2. Complete a Risk Assessment:** Evaluate identified risks related to budgets, controls, internal processes, and regulations.
* **3. Conduct the Audit:** Assess the security of identified assets listed in the audit scope.
* **4. Create a Mitigation Plan:** Establish strategies to lower risk levels, penalties, and potential costs.
* **5. Communicate Results:** Provide detailed findings, improvement suggestions, and relevant compliance standards to stakeholders.

### ⚖️ Common Compliance Regulations

* **GDPR (General Data Protection Regulation):** Protects EU citizens' data processing and privacy rights both in and out of EU territory; mandates informing authorities/individuals of breaches within 72 hours.
* **PCI DSS (Payment Card Industry Data Security Standard):** International standard ensuring secure environments for organizations that store, accept, process, and transmit credit card information.
