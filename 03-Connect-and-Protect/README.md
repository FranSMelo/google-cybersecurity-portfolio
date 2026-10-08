# 📂 Course 3: Connect and Protect: Networks and Network Security

## 📌 Overview

This course introduced the foundations of network security and showed how communication systems, protocols, and connected devices create both business value and attack surfaces. It focused on understanding network architecture, how data moves across networks, how common attacks exploit weaknesses, and how cybersecurity professionals use hardening measures to protect systems and people.

The work in this folder reflects the course’s four modules and the supporting network analysis, hardening, and incident-response materials I developed during this stage of the Google Cybersecurity Certificate.

## 🧭 Course 3 Modules at a Glance

### Module 1: Network architecture

This module introduced the building blocks of network design and security. I explored how networks are structured, how devices such as routers, switches, firewalls, and access points communicate, and how a well-designed architecture supports both performance and security.

### Module 2: Network operations

This module focused on the protocols and processes that allow devices to communicate. I studied the TCP/IP and OSI models, packet flow, addressing, and communication basics such as IP, TCP, UDP, and ICMP. It also covered how network operations can create vulnerabilities if traffic is not properly filtered, monitored, and protected.

### Module 3: Secure against network intrusions

This module examined network-based attacks, especially Denial of Service (DoS) and distributed denial of service (DDoS) activity, and how attackers exploit protocol weaknesses. I learned how to recognize abnormal traffic patterns, analyze protocol behavior, and identify ways to mitigate attacks such as SYN floods and ICMP floods.

### Module 4: Security hardening

This module focused on reducing risk through defensive configuration. I explored security hardening practices such as firewall maintenance, disabling unused ports, implementing least privilege, enforcing password and access controls, patching systems, and using monitoring and logging to detect malicious activity.

## 🔐 What I Learned

- How networks are designed and how different devices contribute to communication and security.
- How the TCP/IP and OSI models help explain network communication and troubleshooting.
- The role of IP addressing, MAC addressing, DNS, TCP, UDP, and ICMP in network operations.
- How protocols can become attack vectors when misconfigured or exposed.
- How common network attacks, such as SYN floods and ICMP floods, disrupt service availability.
- How tools like Wireshark and tcpdump help investigate network traffic and identify root causes.
- The importance of firewalls, IDS/IPS, access controls, monitoring, and patch management in protecting networks.
- How security hardening reduces risk and strengthens resilience across on-premise and cloud environments.

## 🧪 Practical Exercises and Deliverables

This section includes the work completed during the course, including notes, packet-analysis reports, and security-hardening documentation.

- [M3-Notes.md](./M3-Notes.md) — Core study notes covering network architecture, protocols, security controls, and course concepts.
- [Network-hardening.tools.md](./Network-hardening.tools.md) — Summary of network hardening tasks and the purpose of key defensive measures.
- [incident-report-analysis-NIST.md](./incident-report-analysis-NIST.md) — NIST CSF-aligned incident analysis covering detection, protection, response, and recovery.
- [incident-report-network-analysis-TCPDUMP.md](./incident-report-network-analysis-TCPDUMP.md) — Analysis of a DNS/ICMP service outage captured with tcpdump.
- [incident-report-network-analysis-Wireshark.md](./incident-report-network-analysis-Wireshark.md) — Investigation of a SYN flood attack using Wireshark traffic analysis.
- [Security-Risk-Assessment-Report.md](./Security-Risk-Assessment-Report.md) — Risk assessment and incident response evaluation connected to cybersecurity decision-making.
- [tcpdump-log.md](./tcpdump-log.md) — Packet-level log interpretation explaining the DNS and ICMP failures seen during the network investigation.

## 📚 Core Study Notes

### Network architecture and communication

- A network is a group of connected devices that share resources and exchange information.
- Network architecture describes how devices, services, and traffic paths are organized.
- Common network components include routers, switches, firewalls, servers, access points, and endpoints such as desktops and mobile devices.
- A firewall acts as a barrier between trusted internal networks and untrusted external networks.
- Network diagrams help analysts understand where assets are positioned and where threats could enter.

### Protocols and network operations

- The TCP/IP model provides a practical way to understand network communication through four layers: Network Access, Internet, Transport, and Application.
- The OSI model is a conceptual seven-layer model used to describe communication functions.
- IP is responsible for addressing and routing packets between hosts.
- TCP is connection-oriented and reliable; it establishes a three-way handshake before transmitting data.
- UDP is connectionless and faster but less reliable; it is commonly used for services such as DNS and streaming.
- ICMP is used for message and error reporting, such as destination unreachable or host unreachable notifications.
- DNS resolves domain names to IP addresses so clients can access websites and services.

### Network attacks and intrusion risks

- A SYN flood is a DoS technique where an attacker sends many TCP SYN requests without completing the handshake.
- An ICMP flood overwhelms a target with excessive ping traffic and can consume bandwidth and system resources.
- DNS failures can prevent users from resolving hostnames to IP addresses, causing service outages.
- Untrusted external traffic and spoofed source addresses can be used to bypass normal filtering and overwhelm systems.
- Detecting and stopping malicious traffic early is critical to maintaining service continuity.

### Security hardening and defensive controls

- Security hardening involves reducing exposure by strengthening system configuration and network design.
- Common hardening tasks include disabling unused ports, updating patches, enforcing MFA, reviewing access privileges, and maintaining firewall rules.
- Network logging and monitoring help detect suspicious traffic patterns and support investigations.
- A layered defensive strategy combines prevention, detection, response, and recovery.
- Hardening is especially important in cloud and hybrid environments, where virtual networking services and remote infrastructure increase complexity.

## 🛡️ Key Security Concepts Covered

- **Firewall:** A security device or service that inspects and filters traffic based on rules.
- **IDS / IPS:** Tools that detect malicious activity and can also block suspicious traffic in real time.
- **DNS:** Domain Name System used to translate human-readable names into IP addresses.
- **TCP:** Connection-oriented protocol for reliable communication.
- **UDP:** Lightweight connectionless protocol used for quick communication.
- **ICMP:** Protocol used for error and connectivity messages.
- **DoS / DDoS:** Attack methods that overwhelm network services and disrupt availability.
- **Hardening:** A set of actions taken to reduce vulnerabilities and strengthen security.
- **Least privilege:** Granting only the access required for a user or system to perform its function.
- **Monitoring and logging:** Continuous observation of network traffic and system events to detect issues and investigate incidents.

## 📌 Notable Incident Investigations

Two of the most valuable exercises in this course involved interpreting real-world-style traffic logs and identifying the likely causes of service disruption.

### DNS outage investigation

The tcpdump analysis showed repeated DNS queries followed by ICMP `udp port 53 unreachable` responses. This indicated that the DNS service on UDP port 53 was unavailable or blocked. Because the hostname could not be resolved, users could not reach the website normally.

### SYN flood investigation

The Wireshark analysis revealed a large volume of SYN requests to a web server from an external source. The logs matched the behavior of a TCP SYN flood: the server was receiving multiple connection attempts without completing the handshake, exhausting system resources and resulting in timeouts for legitimate users.

## 🗂️ Folder Contents

```text
03-Connect-and-Protect/
├── README.md
├── M3-Notes.md
├── Network-hardening.tools.md
├── Security-Risk-Assessment-Report.md
├── incident-report-analysis-NIST.md
├── incident-report-network-analysis-TCPDUMP.md
├── incident-report-network-analysis-Wireshark.md
├── tcpdump-log.md
└── image/
```

## 💡 Key Takeaway

Course 3 showed that secure networks do not simply rely on connectivity—they require thoughtful design, strong visibility, layered protection, and continuous monitoring. Understanding how traffic flows, how protocols behave, and how attackers exploit weaknesses is essential for protecting organizations against network intrusions and service disruptions.

This module strengthened my understanding of how cybersecurity professionals defend digital environments by combining architecture awareness, protocol analysis, incident response, and network hardening.

