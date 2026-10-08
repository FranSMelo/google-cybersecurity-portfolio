# Cybersecurity Incident Report & Risk Assessment (NIST CSF)

**Organization:** Enterprise Multimedia & Digital Services (Web Design, Graphic Design, and Social Media Marketing Solutions)
**Framework Applied:** National Institute of Standards and Technology Cybersecurity Framework (NIST CSF)
**Incident Classification:** Volume-Based Denial of Service (DoS) via ICMP Flooding

---

## 1. Executive Summary & Incident Overview

An unmitigated volumetric **Denial of Service (DoS)** attack severely compromised the organization's internal network infrastructure for a duration of two hours, leading to a complete disruption of network services and blocking normal internal traffic from accessing essential enterprise resources.

Root cause analysis confirmed that an external threat actor leveraged an **unconfigured firewall** at the perimeter to flood the network with high-rate ICMP pings. This lack of initial filtering and rate controls allowed the malicious traffic to overwhelm network links and processing queues. The incident management team successfully executed emergency containment by blocking incoming ICMP packets, taking non-critical network services offline, and restoring core critical services.

To prevent recurrence, the network security team implemented robust protective measures: rate-limiting rules, source IP verification, network monitoring tools, and an integrated Intrusion Detection and Prevention System (IDS/IPS).

---

## 2. Identify (Asset Management, Risk Assessment, & Business Environment)

To establish a clear understanding of the security gaps and organizational impact, the incident was analyzed across multiple dimensions:

* **Attack Vector & Vulnerability Analysis:**
  * **Root Cause:** An unconfigured perimeter firewall lacking basic packet filtering and rate-limiting rules.
  * **Methodology:** Malicious actors injected a high-volume flood of ICMP ping packets directly into the corporate network boundary, exploiting the lack of ingress filtering.
* **Technology & Asset Inventory:**
  * **Perimeter Defenses:** Unconfigured firewalls that failed to inspect or drop unrequested external traffic, leading to resource exhaustion.
  * **Core Network & Servers:** Internal servers supporting web design, graphic design, and social media marketing operations experienced total link saturation, making remote and local access impossible.
* **Process & Business Impact:**
  * Complete operational standstill for two hours, preventing staff from executing client deliverables, accessing marketing repositories, and utilizing internal communication channels.
* **Personnel & Stakeholder Scope:**
  * Internal network users, IT support staff, and the incident management team were directly impacted and mobilized to handle triage, isolation, and recovery.

---

## 3. Protect (Safeguards, Access Control, & Defensive Hardening)

To eliminate the architectural and configuration vulnerabilities exposed during the DoS event, the organization deployed structured defensive controls:

* **Perimeter Firewall Hardening & Ingress Filtering:**
  * **Rate-Limiting Rules:** Configured specific firewall policies to restrict and regulate the incoming rate of ICMP traffic, preventing bandwidth exhaustion.
  * **Source IP Verification:** Implemented source IP address verification checks on the firewall to actively inspect and drop incoming packets carrying spoofed or non-routable source addresses.
* **Deployment of Dedicated Protective Technology:**
  * **IDS/IPS Integration:** Deployed an Intrusion Detection and Prevention System (IDS/IPS) inline to automatically inspect and filter out ICMP traffic exhibiting suspicious characteristics or anomalous volume signatures before reaching internal segments.
* **Proactive Network Visibility:**
  * Established baseline network monitoring procedures to continuously oversee device health and traffic hygiene at the perimeter.

---

## 4. Detect (Continuous Monitoring, Anomalies, & Event Detection)

To ensure rapid identification of future anomalies and prevent prolonged service degradation, the detection strategy focuses on continuous monitoring:

* **Network Monitoring Software:**
  * Deployed dedicated network monitoring tools to continuously observe device traffic patterns, bandwidth utilization, and baseline performance metrics.
* **Anomaly & Threat Tracking:**
  * Configured detection mechanisms to specifically track incoming external ICMP packets originating from non-trusted or suspicious IP addresses attempting to traverse the firewall.
* **Early Warning Indicators:**
  * Enhanced monitoring capabilities to ensure that sudden volume spikes or unauthorized traffic signatures trigger immediate alerts for the security team.

---

## 5. Respond (Incident Response Plan, Mitigation, & Communication)

To standardize future responses to similar volumetric attacks and minimize downtime, the organization established a clear response framework:

* **Immediate Containment Actions:**
  * Rapid execution of emergency isolation procedures: manually blocking incoming malicious ICMP packet streams at the firewall boundary and taking non-critical network services offline to preserve computational and bandwidth resources for critical operations.
* **Threat Neutralization & Filtering:**
  * Utilizing the newly deployed IDS/IPS and firewall rate-limiting rules to neutralize active attack traffic streams and filter out malicious characteristics.
* **Forensic Data & Analysis:**
  * Reviewing network monitoring logs, firewall event histories, and traffic patterns to analyze the source, scope, and impact of the security event, feeding lessons learned back into operational playbooks.

---

## 6. Recover (System Restoration, Business Continuity, & Lessons Learned)

Restoring operational integrity requires a controlled, structured recovery process to ensure full service availability without lingering risks:

* **Phased Service Restoration:**
  * Under the guidance of the incident management team, critical network services were systematically restored to normal operational status once threat mitigation rules were validated.
* **Resuming Normal Operations:**
  * Controlled bring-up of non-critical network services, ensuring that normal internal network traffic regained secure, unhindered access to all required resources.
* **Process Refinement & Business Continuity:**
  * Evaluated the recovery timeline of the two-hour outage to refine future incident response workflows, ensuring faster communication, streamlined restoration, and enhanced resilience against future network threats.

---

## 7. Reflections & Strategic Takeaways

* **The Importance of Baseline Configuration:** A default or unconfigured firewall leaves critical enterprise perimeters exposed to basic volumetric exploits like ICMP floods.
* **Proactive Security Integration:** Combining reactive containment (such as emergency service throttling) with proactive defenses (rate-limiting, source verification, and IDS/IPS filtering) creates a resilient posture that safeguards business continuity.
