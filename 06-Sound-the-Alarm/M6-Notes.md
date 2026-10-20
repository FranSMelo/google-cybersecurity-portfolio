# 📚 Introduction to Detection and Incident Response

## 👥 Incident Response Framework & Organizational Roles (CSIRT & SOC)

### 🔄 NIST Incident Response Lifecycle

The National Institute of Standards and Technology (NIST) defines a four-phase framework for managing and responding to cybersecurity incidents:

#### 1. Preparation

* **Focus:** Establishing controls, tools, policies, and training before an incident occurs.
* **Activities:** Setting up monitoring tools, establishing incident response plans, configuring logging, and training staff.

#### 2. Detection and Analysis

* **Focus:** Identifying security events, determining their scope, and confirming whether an incident has occurred.
* **Activities:** Triaging alerts, analyzing security log data, identifying IOCs (Indicators of Compromise), and investigating root causes.

#### 3. Containment, Eradication, and Recovery

* **Focus:** Limiting incident damage, eliminating the threat actor or malware, and safely restoring systems to normal operations.
* **Activities:** Isolating affected network segments (containment), deleting malicious code/patching gaps (eradication), and restoring systems from clean backups (recovery).

#### 4. Post-Incident Activity

* **Focus:** Learning from the event to improve future security posture.
* **Activities:** Conducting "lessons learned" meetings, finalizing official incident reports, preserving digital evidence, and refining response plans.

### 📌 Core Command Framework

* **Command, Control, and Communication ($3C$s):** Effective incident management relies on three core pillars:
  * **Command:** Providing leadership and direction to oversee the entire response.
  * **Control:** Managing technical aspects, coordinating resources, and assigning tasks.
  * **Communication:** Keeping internal and external stakeholders informed of incident status.

### 🛡️ Computer Security Incident Response Teams (CSIRTs)

A **CSIRT** is a specialized group of security and non-security professionals trained in incident management and response. They can be structured as dedicated teams or ad-hoc task forces.

#### Key CSIRT Roles

* **Security Analyst:** Continuously monitors the environment, analyzes and triages alerts, performs root-cause investigations, and escalates critical threats.
* **Technical Lead:** Manages all technical aspects of the response (e.g., determining root cause, patching vulnerabilities, and executing containment, eradication, and recovery strategies).
* **Incident Coordinator (Manager / Commander):** Oversees communication and cross-collaboration with external and non-security departments (such as HR, Legal, PR, and Executive Management).
* **Supporting Roles:** Dedicated communications leads, legal leads, and planning leads depending on organizational scale.

#### 🏢 Security Operations Center (SOC) Structure

A **SOC** (often aligned with "Blue Team" defensive operations) is a dedicated unit responsible for continuous network and system monitoring. SOC analysts are structured across a tiered hierarchy:

| Tier / Role                       | Experience Level            | Core Responsibilities                                                                                                          |
| :-------------------------------- | :-------------------------- | :----------------------------------------------------------------------------------------------------------------------------- |
| **Tier 1 SOC Analyst (L1)** | Junior / Least Experienced  | Monitors, reviews, and prioritizes alerts; manages ticketing systems (creating/closing alerts); escalates tickets to Tier 2/3. |
| **Tier 2 SOC Analyst (L2)** | Intermediate / Experienced  | Investigates escalated L1 tickets deeply; configures and refines security monitoring tools; reports to SOC Leads.              |
| **Tier 3 SOC Lead (L3)**    | Senior / Highly Experienced | Manages team operations; performs advanced threat detection, malware analysis, and digital forensics; reports to SOC Managers. |
| **SOC Manager**             | Executive / Top Tier        | Handles hiring, training, and team performance metrics; manages compliance, auditing, and executive reporting.                 |

#### Specialized SOC Roles

* **Forensic Investigators:** Typically L2 or L3 analysts specializing in the collection, preservation, and analysis of digital evidence to reconstruct incident timelines.
* **Threat Hunters:** Senior L3 analysts who proactively seek out, analyze, and mitigate advanced threats using threat intelligence before traditional alerts trigger.

## 🔍 Cybersecurity Detection Tools (IDS, IPS, & EDR)

### 📌 Importance of Detection Tools

* **Core Purpose:** Cybersecurity detection tools continuously monitor networks, systems, and endpoints for unauthorized access or malicious behavior—similar to how physical home security systems monitor for physical intrusions.
* **Visibility & Alerting:** They provide real-time operational awareness to security analysts by generating alerts when anomalies or threat indicators are detected, enabling prompt incident investigation and response.

### 🛠️ Feature Comparison Matrix

Security analysts must understand the capabilities and operational scopes of **IDS**, **IPS**, and **EDR** solutions:

| Capability                                     | IDS (Intrusion Detection System) | IPS (Intrusion Prevention System) | EDR (Endpoint Detection & Response) |
| :--------------------------------------------- | :------------------------------- | :-------------------------------- | :---------------------------------- |
| **Detects Malicious Activity**           | ✅                               | ✅                                | ✅                                  |
| **Prevents Intrusions / Blocks Attacks** | ❌ (Alerts only)                 | ✅                                | ✅                                  |
| **Logs Activity**                        | ✅                               | ✅                                | ✅                                  |
| **Generates Alerts**                     | ✅                               | ✅                                | ✅                                  |
| **Performs Behavioral Analysis (AI/ML)** | ❌                               | ❌                                | ✅                                  |
| **Deployment Location**                  | Network / Host Level             | Network Inline / Host Level       | Installed Directly on Endpoints     |

### 📡 Intrusion Detection Systems (IDS)

* **Definition:** A passive monitoring application that analyzes system or network traffic to identify potential security threats and trigger alerts without taking automated blocking actions.
* **Operational Example:** Flagging an login attempt coming from an unapproved geographic IP address or at an unusual hour.
* **Common IDS Tools:** **Zeek**, **Suricata**, **Snort®**, and **Sagan**.

#### 📊 The 4 Detection States (Alert Categories)

When investigating alerts generated by detection engines, analysts categorize outcomes using a standard matrix:

| Detection Category            | Actual Threat Present? | Alert Generated? | Analysis & Impact                                                                                                      |
| :---------------------------- | :--------------------- | :--------------- | :--------------------------------------------------------------------------------------------------------------------- |
| **True Positive (TP)**  | Yes                    | Yes              | **Correct Detection:** An actual attack occurred and was successfully flagged.                                   |
| **True Negative (TN)**  | No                     | No               | **Normal Operations:** System traffic is benign and no alert was triggered.                                      |
| **False Positive (FP)** | No                     | Yes              | **Inconvenience / Noise:** Legitimate traffic flagged as malicious; wastes analyst time and SOC resources.       |
| **False Negative (FN)** | Yes                    | No               | **Dangerous Miss:** A real attack occurred but evaded detection completely, leaving the organization vulnerable. |

### 🛡️ Intrusion Prevention Systems (IPS)

* **Definition:** An active detection application that monitors traffic for intrusive activity, triggers alerts, and **automatically executes preventive countermeasures** to stop the attack.
* **Operational Example:** Automatically updating a router's Access Control List (ACL) or firewall rule to drop traffic originating from an attacking IP address.
* **Dual-Mode Capabilities:** Many industry tools (e.g., **Suricata**, **Snort**, **Sagan**) can operate as either an IDS (passive mode) or an IPS (inline active mode).

### 💻 Endpoint Detection & Response (EDR)

* **Definition:** An endpoint-installed application that continuously monitors, records, and analyzes activity on connected host devices (workstations, servers, smartphones, laptops).
* **Behavioral Analysis:** Leverages machine learning (ML) and artificial intelligence (AI) to evaluate runtime behavior patterns and spot unknown or zero-day threats.
* **Automated Response:** Executes host-level responses without human intervention (e.g., terminating an unauthorized process, isolating a host from the network, or rolling back malicious file modifications).
* **Common EDR Tools:** **Open EDR®**, **Bitdefender™ EDR**, and **FortiEDR™**.


## 📊 Security Information and Event Management (SIEM) Technology

* **Security Information and Event Management (SIEM):** A security application that collects, aggregates, normalizes, and analyzes log data across an enterprise environment to monitor critical activities in real time.
* **Log Analysis:** The process of examining consolidated event logs to identify threats, anomalous behaviors, and security events of interest.
* **Key Advantages:**
  * **Unified Event Data Access:** Ingests and centralizes real-time data from hundreds of disparate network devices, firewalls, servers, and applications.
  * **Real-Time Monitoring & Alerting:** Continuously evaluates log data using detection logic and rule sets, generating alerts for immediate SOC triage.
  * **Centralized Data Retention & Historical Search:** Functions as a long-term data store for compliance, auditing, and historical forensic investigations.

### 🔄 The 3-Step SIEM Process

SIEM platforms follow a structured three-phase pipeline to transform raw log output into actionable security intelligence:

#### 1. Collect, Aggregate & Parse Data

* **Collection & Aggregation:** Centralizes log data from firewalls, routers, servers, and applications into a single platform, eliminating manual per-device log reviews.
* **Data Parsing:** Extracts key key-value pairs (timestamps, IP addresses, port numbers, usernames) from raw log strings.
  * *Raw Log Example:* `April 3 11:01:21 server sshd[1088]: Failed password for user nuhara from 218.124.14.105 port 5023`
  * *Parsed Output:*
    * `host`: server
    * `process`: sshd
    * `source_user`: nuhara
    * `source_ip`: 218.124.14.105
    * `source_port`: 5023

#### 2. Normalize Data

* **Definition:** Transforms disparate log formats from different vendors (e.g., firewall logs vs. Windows Event Logs) into a standardized, unified schema.
* **Impact:** Ensures log data is consistent, structured, and rapidly searchable across the entire enterprise stack.

#### 3. Analyze Data

* **Detection Rules:** Applies detection logic, thresholds, and conditions to normalized data streams.
* **Event Correlation:** Cross-references and links multiple separate log events (e.g., matching a failed SSH login on a server with an outbound port scan on a firewall) to uncover sophisticated threat patterns and trigger SOC alerts.

### 🛠️ Industry-Standard SIEM Tools

Security analysts frequently utilize these enterprise SIEM platforms:

* **AlienVault® OSSIM™**
* **Chronicle**
* **Elastic Security**
* **Exabeam**
* **IBM QRadar®**
* **LogRhythm**
* **Splunk®**
