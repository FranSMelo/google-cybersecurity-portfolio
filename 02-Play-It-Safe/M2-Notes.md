# 📚 Security domains

## 🛡️ The 8 CISSP Security Domains

![j1FbNS82S1yYlxE-Igbeww_15365b8830a9459285e35f2c933705f1_1oSzH-WlqUZe0MTeQnysKIvtlhXgJLES9dw5McvmUZL-EwfcEQLEDVcXErzxOnVYOJlIqqAK1mafq5Oq9C3lniHKrVvbcChb4_eChT-nusF47qadYlvZV05YzW302o7kstvEsIOw48J8Op_AsTU793sNiXroLTeq8gCo5KrOZiNiIqp6f2P0PLfdfv-BBQ (1600×933)](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/j1FbNS82S1yYlxE-Igbeww_15365b8830a9459285e35f2c933705f1_1oSzH-WlqUZe0MTeQnysKIvtlhXgJLES9dw5McvmUZL-EwfcEQLEDVcXErzxOnVYOJlIqqAK1mafq5Oq9C3lniHKrVvbcChb4_eChT-nusF47qadYlvZV05YzW302o7kstvEsIOw48J8Op_AsTU793sNiXroLTeq8gCo5KrOZiNiIqp6f2P0PLfdfv-BBQ?expiry=1791019065984&hmac=Krj0FwTnfvtUpuETK9zbgO7FeyAngf2wG1fc3MTMuVk)

**Source:** Google Cybersecurity Professional Certificate, Google/Coursera, course material. Image used for educational/reference purposes.

---

### 🔒 1. Security and Risk Management

* **Focus:** Developing and maintaining an organization's overall security posture and defense capabilities against changes and threats.
* **Key Elements:** Security goals, risk mitigation processes, compliance (e.g., GDPR), business continuity plans, legal regulations, and professional ethics.
* **InfoSec Processes:** Incident response, vulnerability management, application security, cloud security, and infrastructure security.

---

### 📦 2. Asset Security

* **Focus:** Managing cybersecurity processes for organizational assets, including storage, maintenance, retention, and destruction of physical and virtual data.
* **Key Elements:** Accurate asset/data tracking, security impact analysis, recovery plans, and data exposure management.
* **Practical Example:** Creating and managing backups to ensure environment restoration during a security incident.

---

### 🏗️ 3. Security Architecture and Engineering

* **Focus:** Managing data security through effective tools, systems, and processes created by security architects and engineers.
* **Key Elements:** Shared responsibility, threat modeling, least privilege, defense in depth, fail securely, separation of duties, and Zero Trust architecture.
* **Practical Example:** Using SIEM (*Security Information and Event Management*) tools to monitor for unusual login or user activity.

---

### 🌐 4. Communication and Network Security

* **Focus:** Managing and securing physical networks, wireless communications, and remote, hybrid, or on-site work environments.
* **Key Elements:** Network security controls (such as restricted network access) and external connection management for remote workers.
* **Objective:** Ensuring data remains secure regardless of employee locations.

---

### 🔑 5. Identity and Access Management (IAM)

* **Focus:** Ensuring user identities are trusted and authenticated, authorizing access only to legitimate physical and logical assets.
* **Core Principle:** Least privilege (granting only the minimal access required to complete a task).
* **Practical Example:** Granting temporary access to customer data to a support representative only while resolving an issue, then removing access afterward.

---

### 🔍 6. Security Assessment and Testing

* **Focus:** Proactively identifying and mitigating risks, threats, and vulnerabilities across internal systems.
* **Key Elements:** Penetration testing (*pen testers*), security control testing, data collection, audits, and user permission validation.
* **Objective:** Reducing the probability of a data breach by catching flaws before threat actors do.

---

### 🚨 7. Security Operations

* **Focus:** Investigating potential data breaches and implementing preventative measures after a security incident occurs.
* **Key Elements:** Training and awareness, reporting/documentation, intrusion detection and prevention, SIEM tools, log management, incident management, playbooks, post-breach forensics, and lessons learned.
* **Objective:** Managing and mitigating active attacks in real-time to protect private information.

---

### 💻 8. Software Development Security

* **Focus:** Applying secure programming practices and guidelines throughout the entire Software Development Life Cycle (SDLC).
* **Key Elements:** Security must be integrated from design through testing and release (never an afterthought), application testing, and quality assurance (QA).
* **Practical Example:** Ensuring proper encryption configuration for a new medical device storing private patient data.

---

# 📉 Managing Security Risks and Threats

## 🔍 Understanding Risk Management

* **Focus:** Protecting organizational assets (both digital and physical) from threats, risks, and vulnerabilities using frameworks like the NIST Risk Management Framework (RMF) and HITRUST.
* **Key Elements:**
  * **Digital Assets:** Personal identifiable information (PII) such as Social Security Numbers (SSNs), dates of birth, bank account numbers, and mailing addresses.
  * **Physical Assets:** Payment kiosks, servers, desktop computers, and office spaces.
* **Risk Management Strategies:**
  * **Acceptance:** Accepting a risk to avoid disrupting business continuity.
  * **Avoidance:** Creating a plan to avoid the risk altogether.
  * **Transference:** Transferring risk to a third party to manage.
  * **Mitigation:** Lessening the impact of a known risk.

---

## ⚠️ Today’s Most Common Threats, Risks, and Vulnerabilities

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
