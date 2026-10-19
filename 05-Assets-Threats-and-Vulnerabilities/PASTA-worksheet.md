# Sneaker Marketplace Mobile App - PASTA Threat Model Report

## Exercise Overview & Threat Modeling Methodology

This cybersecurity report documents a threat modeling assessment performed for a growing sneaker enthusiast and collector company preparing to launch a new mobile commerce application. The application allows buyers and users to securely search inventory, communicate directly with sellers, rate services, and process financial transactions.

To systematically evaluate the security posture and risk profile of the application, the assessment follows the **Process of Attack Simulation and Threat Analysis (PASTA)** framework across its seven distinct stages:

1. **Define Business and Security Objectives:** Aligning security requirements with operational goals (data privacy, smooth transactions, secure payments).
2. **Define Technical Scope:** Evaluating core technologies (API, PKI, AES, SHA-256, SQL) and prioritizing high-risk components.
3. **Decompose Application:** Analyzing data flow diagrams (DFDs) to map out user queries and data handling processes.
4. **Threat Analysis:** Identifying internal and external threat sources and potential threat events.
5. **Vulnerability Analysis:** Pinpointing software flaws, database weaknesses, and architectural gaps using resources like OWASP and CVE.
6. **Attack Modeling:** Constructing attack trees to visualize exploitation paths (e.g., SQL injection and session hijacking).
7. **Risk Analysis & Defenses:** Implementing robust technical, operational, and managerial security controls to mitigate risk.

---

## PASTA Worksheet & Stage Breakdown

### Stage I: Define Business and Security Objectives

* **Business Requirements & Objectives:**
  1. Seamlessly connect buyers and sellers while ensuring high data privacy standards and responsible handling of Personally Identifiable Information (PII).
  2. Provide a reliable, quick checkout process with multiple payment options while strictly avoiding regulatory and legal liability regarding financial data.
  3. Support messaging and rating systems to foster user trust and community engagement.

### Stage II: Define Technical Scope & Prioritization

* **Core Technologies:** API, PKI, AES, SHA-256, SQL.
* **Prioritization Rationale:**
  SQL and APIs are prioritized over other technologies because they directly handle external user requests and interact with backend databases storing sensitive inventory and user records. Securing database queries and API endpoints is critical to prevent injection attacks and unauthorized data exfiltration before addressing encryption standards.

### Stage III: Decompose Application (Data Flow Analysis)

* **Process Decomposition:** The application data flow diagram illustrates a user searching for inventory. The user sends a search query through the mobile interface, which passes through backend processing logic and queries the SQL database to return current listings. Securing this flow requires ensuring that inputs are sanitized before reaching the database.

### Stage IV: Threat Analysis

* **Identified Threats:**
  1. **External SQL Injection Attacks:** Malicious actors attempting to manipulate search queries or login fields to extract unauthorized database contents.
  2. **Session Hijacking / Credential Theft:** Attackers intercepting user sessions or exploiting weak authentication mechanisms to gain unauthorized account access.

### Stage V: Vulnerability Analysis

* **Identified Vulnerabilities:**
  1. **Lack of Prepared Statements / Input Validation:** Vulnerabilities in the codebase that permit malicious SQL commands to be executed directly against the database engine.
  2. **Weak Authentication Mechanisms:** Flaws in credential handling or session management allowing unauthorized token capture and reuse.

### Stage VI: Attack Modeling

* **Attack Tree Summary:** Attack paths branch from compromising user data through two primary vectors: exploiting database interaction flaws via SQL injection (rooted in a lack of prepared statements) and compromising authentication via session hijacking (rooted in weak login credentials).

### Stage VII: Risk Analysis and Defense Strategies

* **Recommended Security Controls:**
  1. **Parameterized Queries / Prepared Statements:** Neutralize SQL injection vectors by separating user input from database command execution.
  2. **Multi-Factor Authentication (MFA):** Strengthen user and administrator login security to prevent session hijacking.
  3. **End-to-End Encryption (AES/PKI):** Ensure sensitive data at rest and in transit (especially credit card numbers and session tokens) is heavily encrypted.
  4. **Role-Based Access Control (RBAC) & Least Privilege:** Restrict user and API privileges to only the resources strictly required for their operational functions.

---

## Summary

By applying the PASTA threat model framework, the security team successfully mapped the attack surface, identified critical database and authentication vulnerabilities, and established a prioritized defense-in-depth remediation strategy. This ensures the sneaker marketplace application can launch securely, maintaining user trust and regulatory compliance.
