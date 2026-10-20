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

---

---

# 📚 Network monitoring and analysis

📡 Network Monitoring & Baselining

* **Network Monitoring:** The continuous collection, analysis, and evaluation of network traffic and network data to maintain situational awareness and protect against security incidents.
* **Network Traffic vs. Network Data:**
  * **Network Traffic:** The volume and types of data moving across a network (e.g., HTTP, HTTPS, SSH traffic).
  * **Network Data:** The actual data payload and headers transmitted between connected devices on a network.
* **Establishing a Baseline:** A reference point used to define expected or normal network behavior, traffic volumes, and communication patterns. Baselines allow security analysts to identify abnormal network deviations, unexpected traffic spikes, or unauthorized connections.

### 🔍 Key Network Components to Monitor

Security analysts examine specific network telemetry elements to detect anomalies and potential Indicators of Compromise (IoCs):

| Network Telemetry Component          | Description & Operational Focus                                                                                      | Threat Indicators & Detection Examples                                                                                                                |
| :----------------------------------- | :------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Flow Analysis**              | Analyzes the movement of network communications, including packet headers, protocols, and port numbers.              | Unapproved ports, mismatched protocol/port pairings (e.g., HTTPS running over port 8088 instead of port 443), and Command and Control (C2) beaconing. |
| **Packet Payload Information** | The actual transmitted data contained within a network packet. Often requires decryption for deep packet inspection. | Unencrypted sensitive data, data exfiltration attempts, and embedded malware signatures.                                                              |
| **Temporal Patterns**          | Evaluates time-based patterns and timestamps associated with network traffic flows.                                  | Large traffic bursts occurring outside normal business hours (e.g., massive data transfers at 2:00 AM).                                               |

### 🏢 Operational Monitoring Units: SOC vs. NOC

Organizations deploy specialized units to balance network security and operational uptime:

* **Security Operations Center (SOC):** Focuses on maintaining security, identifying Indicators of Compromise (IoCs), and managing incident detection and response.
* **Network Operations Center (NOC):** Focuses on maintaining network performance, availability, bandwidth utilization, and mitigating network outages or disruptions.

### 🛠️ Network Monitoring Tools

Network monitoring is conducted using both automated detection engines and manual packet analysis utilities:

* **Intrusion Detection Systems (IDS):** Automated tools (such as Snort, Suricata, or Zeek) that continuously monitor packet payloads and traffic flows against configured baseline rules to trigger security alerts.
* **Network Protocol Analyzers (Packet Sniffers):** Utilities used to capture, record, and inspect live network traffic packet captures (PCAP files) at a granular level.
  * **tcpdump:** A command-line packet capture and analysis tool.
  * **Wireshark:** A graphical user interface (GUI) network protocol analyzer used for deep packet inspection.

## 📦 Deep Dive into Packet Captures and Network Analysis

* **Packet Analysis:** The granular examination of data packets moving across a network to investigate security events, detect anomalies, and uncover Indicators of Compromise (IoCs).
* **Packet Capture (PCAP):** A file containing raw data packets intercepted from a network interface or segment, which can be stored, filtered, and analyzed using network protocol analyzers.

### 🧩 Structure of a Network Packet

Every data packet traveling across a network is broken down into three primary components:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/Mi_kryGkRiyYUOJDIwnPCw_ac942d1eec284467a5ca533cb99c4bf1_S20G003.png?expiry=1792576118414&hmac=5OJVyd_LK4VjpZWeYFnaeQiVCkJScILBKqGRZNbyugc)

1. **Header:** The most critical routing component. Includes Ethernet, IP, and TCP/UDP headers containing source/destination IP addresses, port numbers, packet length, and sequence IDs.
2. **Payload:** The actual data being transported (e.g., file contents, text, images, or application commands). Often requires decryption or deep inspection.
3. **Footer:** Located at the end of the packet, utilized primarily by Ethernet protocols for error-checking (CRC) to detect data corruption. Most protocols (like IP) do not utilize footers.

### 🔍 Network Protocol Analyzers (Packet Sniffers)

* **Definition:** Software or hardware tools designed to capture, record, and inspect live network data traffic.
* **Common Tools:**
  * **tcpdump:** A lightweight, command-line packet capture and analysis tool for Unix-like systems.
  * **Wireshark:** A feature-rich graphical user interface (GUI) packet analyzer used for deep packet inspection.
  * **TShark:** A command-line companion tool to Wireshark.
* **Dual-Use Risk:** While security professionals use protocol analyzers for threat hunting and troubleshooting, malicious actors use packet sniffers to illicitly intercept sensitive data like unencrypted credentials.

### ⚙️ How Packet Sniffing Works

1. **NIC Interface Modes:** By default, a Network Interface Card (NIC) only processes traffic explicitly addressed to its own MAC address. To capture all visible traffic on a segment, the NIC must be placed into specialized modes:
   * **Promiscuous Mode:** Listens to all traffic traveling across a wired network segment.
   * **Monitoring Mode:** Listens to all wireless traffic within range without requiring association to an Access Point.
2. **Binary Conversion:** Network protocol analyzers ingest raw binary data ($0$s and $1$s) from the NIC and convert it into a human-readable format for security analysts.

*⚠️ **Security Note:** Operating in promiscuous mode exposes devices to passive sniffing risks; unauthorized interception of private network communications is illegal in many jurisdictions.*

### 📁 PCAP Libraries and File Formats

Packet capture files are saved in various formats depending on the underlying operating system and capture library:

| PCAP Library / Format | Target Operating System  | Key Characteristics                                                                                                                      |
| :-------------------- | :----------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| **Libpcap**     | Unix-like (Linux, macOS) | The standard packet capture library and format used by tools like `tcpdump`.                                                           |
| **WinPcap**     | Windows (Legacy)         | An older packet capture library for Windows environments, largely superseded.                                                            |
| **Npcap**       | Windows (Modern)         | Modern Windows packet capture library developed by the creators of Nmap.                                                                 |
| **PCAPng**      | Cross-Platform           | **"Next Generation"** PCAP format capable of simultaneously capturing packets, storing metadata, and handling multiple interfaces. |

## 🔬 Investigating Packet Details (IP Headers & Wireshark Analysis)

* **Packet-Level Investigation:** Security incident analysis frequently starts at the packet layer, where data headers contain raw telemetry revealing communication origin, destination, routing behavior, and protocol parameters.
* **Internet Protocol (IP):** The foundational set of networking standards that governs logical addressing and routing of data packets across networks.
* **Wireshark:** A widely adopted open-source graphical network protocol analyzer that decodes raw binary network traffic into structured, human-readable packet details and protocol streams.

### 📄 IPv4 vs. IPv6 Header Comparison

Understanding header architecture enables security analysts to spot anomalies, structural modifications, or evasion tactics (such as TTL manipulation or unexpected fragmentation).

![IPv4 vs IPv6 - Understanding the differences | NetworkAcademy.IO](<https://www.networkacademy.io/sites/default/files/2020-10/comparing%20ipv4-and-ipv6-headers.png>)

| Header Field                    | IPv4 (13 Fields)                                   | IPv6 (8 Fields)       | Operational Function & Security Relevance                                                                               |
| :------------------------------ | :------------------------------------------------- | :-------------------- | :---------------------------------------------------------------------------------------------------------------------- |
| **Version**               | `Version` (4 bits)                               | `Version` (4 bits)  | Identifies the IP protocol version being transmitted ($4$ or $6$).                                                  |
| **Priority / QoS**        | `Type of Service (ToS)`                          | `Traffic Class`     | Classifies and prioritizes traffic delivery handling.                                                                   |
| **Header / Payload Size** | `IHL` & `Total Length`                         | `Payload Length`    | Defines length parameters. IPv6 headers are fixed at 40 bytes.                                                          |
| **Flow Tracking**         | N/A                                                | `Flow Label`        | Maintains packet ordering for specific continuous communication flows.                                                  |
| **Fragmentation Control** | `Identification`, `Flags`, `Fragment Offset` | Extension Headers     | IPv4 manages fragmentation inside the main header; IPv6 relies on extension headers and end-node fragmentation.         |
| **Lifespan / Hop Count**  | `Time to Live (TTL)`                             | `Hop Limit`         | Decremented by routers to prevent infinite loops. Anomalous TTL drops can indicate routing manipulation or middleboxes. |
| **Next Protocol Pointer** | `Protocol`                                       | `Next Header`       | Identifies the encapsulated transport payload (e.g., TCP, UDP, ICMP).                                                   |
| **Error Checking**        | `Header Checksum`                                | Managed at L2/L4      | Validates header integrity. Omitted in IPv6 to improve processing speed.                                                |
| **Addressing**            | 32-bit (e.g., `192.168.1.1`)                     | 128-bit (Hexadecimal) | Identifies sender (`Source`) and receiver (`Destination`).                                                          |

### 🛠️ Wireshark Display Filtering Techniques

Display filters allow security analysts to extract targeted traffic from high-volume packet captures (PCAPs).

#### 1. Comparison & Logical Operators

| Operator Function            |    Symbol    | Abbreviation | Syntax Example                        |
| :--------------------------- | :----------: | :----------: | :------------------------------------ |
| **Equal**              |    `==`    |    `eq`    | `ip.src == 10.10.10.10`             |
| **Not Equal**          |    `!=`    |    `ne`    | `ip.dst != 192.168.1.1`             |
| **Greater Than**       |    `>`    |    `gt`    | `frame.len > 1000`                  |
| **Less Than**          |    `<`    |    `lt`    | `tcp.analysis.ack_rtt < 0.01`       |
| **Greater or Equal**   |    `>=`    |    `ge`    | `tcp.port >= 1024`                  |
| **Less or Equal**      |    `<=`    |    `le`    | `udp.length <= 512`                 |
| **String Containment** | `contains` |     N/A     | `http contains "malware"`           |
| **Regex Match**        | `matches` | `matches` | `http.host matches "(eval\|select)"` |

*💡 **Pro Tip:** Combine filters using logical operators (`and`, `or`, `not`) and parentheses to construct complex queries: `(ip.src == 10.0.0.5 or ip.src == 10.0.0.6) and tcp.port == 443`*

#### 2. Common Filter Expressions

* **Protocol Filtering:** Isolates specific protocol traffic by entering shorthand keywords:
  * `dns`, `http`, `ftp`, `ssh`, `arp`, `telnet`, `icmp`
* **IP & Hardware Addressing:**
  * Host Address: `ip.addr == 172.21.224.2`
  * Source IP: `ip.src == 10.10.10.10`
  * Destination IP: `ip.dst == 4.4.4.4`
  * MAC Address: `eth.addr == 00:70:f4:23:18:c4`
* **Transport Ports:**
  * UDP Port: `udp.port == 53` (DNS)
  * TCP Port: `tcp.port == 80` (HTTP) or `tcp.port == 22` (SSH)

### 🧵 Following Protocol Streams

* **Definition:** A Wireshark feature that reassembles fragmented TCP, UDP, or HTTP payloads from a full conversation back into a sequential, human-readable transcript.
* **Operational Application:**
  * Allows analysts to inspect plain-text application layer transactions (such as HTTP GET/POST requests, response headers, or unencrypted web form inputs).
  * Simplifies tracking interactive sessions (e.g., shell commands executed over unencrypted Telnet or FTP sessions).

## 📋 Overview of tcpdump (Command-Line Packet Analyzer)

* **tcpdump:** A powerful, command-line network protocol analyzer used to capture, inspect, and save network traffic in real time.
* **Command-Line Interface (CLI):** Operates via text-based terminal commands, making it lightweight, scriptable, and pre-installed across most Linux and Unix-like systems (including macOS).
* **Primary Use Cases:** Troubleshooting network performance issues, capturing live traffic, and performing forensic packet analysis during security investigations.

### ⚙️ Basic Syntax & Privileges

Like most packet sniffing tools, `tcpdump` requires administrative or root-level privileges to access the network interface card (NIC) in promiscuous or listening mode:

```bash
sudo tcpdump [-i interface] [option(s)] [expression(s)]
```

* **`sudo`:** Grants the necessary elevated permissions.
* **`-i interface`:** Specifies the network interface to listen on (e.g., `eth0`, `wlan0`, or `any` for all interfaces). Use the `-D` flag to list available interfaces.

### 🛠️ Essential Options (Flags)

Options alter how `tcpdump` executes, writes files, or displays information. Note that options are case-sensitive:

| Option / Flag                       | Description & Operational Function                                                                                                                     | Example Usage                           |
| :---------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------- |
| **`-w`**                    | Writes/saves sniffed packets to a packet capture (PCAP) file instead of printing them to the terminal.                                                 | `sudo tcpdump -i any -w capture.pcap` |
| **`-r`**                    | Reads packets from a specified PCAP file for offline analysis.                                                                                         | `sudo tcpdump -r capture.pcap`        |
| **`-v`, `-vv`, `-vvv`** | Increases verbosity levels to display more detailed packet information (such as IP header fields).                                                     | `sudo tcpdump -r capture.pcap -v`     |
| **`-c`**                    | Specifies a strict packet count limit, stopping the capture after reaching the specified number.                                                       | `sudo tcpdump -i any -c 10`           |
| **`-n`, `-nn`**           | Disables name resolution. `-n` leaves IP addresses un-resolved; `-nn` leaves both IPs and ports un-resolved. Prevents reverse DNS lookup tracking. | `sudo tcpdump -r capture.pcap -nn`    |

### 🔍 Filter Expressions & Boolean Logic

Expressions allow analysts to isolate specific traffic streams, protocols, or endpoints directly within the command:

* **Protocol Filters:** Isolate traffic by protocol type (e.g., `ip`, `ip6`, `tcp`, `udp`, `icmp`).
* **Boolean Operators:** Combine filters using `and`, `or`, and `not`.
* **Grouping & Quoting:** Use single or double quotes around expressions to prevent shell interpretation, and parentheses to control evaluation priority.

#### Example Filter Command

```bash
sudo tcpdump -r packetcapture.pcap -nn 'ip and (port 80 or port 443)'
```

### 📊 Interpreting tcpdump Output

Each line of output generated by `tcpdump` corresponds to an individual captured packet. A standard verbose TCP packet output includes:

1. **Timestamp:** Precise capture time down to fractions of a second (e.g., `12:45:03.123456`).
2. **Source IP & Port:** The origin address and sending port of the packet.
3. **Destination IP & Port:** The receiving address and target port.
4. **Packet Details:** Protocol flags, sequence numbers, window sizes, and additional header data (when verbosity `-v` is enabled).

![Output of a tcpdump command with labels for the timestamp, source IP, source port, destination IP, and destination port.](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/3LnHDkkeQ2-a-KjHKXkBCQ_940eb009d1674c7595f8361adf48c1f1_89by7cw_y0GWsyGI4iK19PqNyVHpVO4reyeIO0v-xYeZDBID0JG0PzpqRSA7fWjmD88HKjaZ8PhlONjdsKMLrUlx0lM9lPGBVSNqO87rZPPHt00BahLIQmfBNpRTyBAgjUklW2nn3hCB5Z-x_0HC56AKW7g2hk4tXgWyjInXVJYMosY9D4pyuX2VzerrhA?expiry=1792582799174&hmac=iP45WNfrtE0V89ML1Spe3PwvpE98kbLnKCbnz5TPcU0)
