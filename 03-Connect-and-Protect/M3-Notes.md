# 📚Network Architecture

## 🌐 Introduction to networks

* **Definition:** Network architecture (or network design) provides a foundational understanding of how networks are structured to help security professionals identify vulnerabilities and malicious exploit attempts.
* **Network Devices:** Specialized hardware and endpoints (such as routers, switches, servers, and workstations) that maintain information, services, and communications over wired and wireless connections via data packets.

### 💻 Key Network Hardware and Devices

* **Devices and Desktop Computers:** End-user devices (PCs, laptops, phones, tablets) featuring a unique MAC address, an IP address, and a network interface to send and receive data packets.
* **Firewalls:** Network security devices acting as a first line of defense to monitor, restrict, and filter incoming/outgoing traffic between secure internal networks and untrusted external resources like the internet.
* **Servers and Clients:** Operating on the client-server model, clients send requests for information and services, while servers (e.g., DNS, file, or mail servers) perform those requests.
* **Hubs vs. Switches:**
  * **Hubs:** Provide a common connection point but broadcast all information out to all ports, making them vulnerable to eavesdropping (rarely used in modern enterprise networks).
  * **Switches:** Preferred over hubs; they forward packets directly to intended devices using a MAC address table, improving performance and security at the data link layer.
* **Routers:** Connect different networks and direct traffic based on destination IP addresses (operating at the network layer), often featuring built-in firewall capabilities to block malicious traffic.
* **Modems and Wireless Access Points:**
  * **Modems:** Connect local networks to an Internet Service Provider (ISP) by translating transmissions/signals.
  * **Wireless Access Points (WAPs):** Create wireless networks via radio waves, allowing devices to connect using Wi-Fi protocols.

### 🗺️ Network Diagrams for Security Analysts

* **Purpose:** Visual maps using representative graphics and connecting lines to portray network architecture and device placement.
* **Analyst Benefit:** By studying network diagrams, security analysts can visualize network design, understand asset layouts, and refine strategies for securing network architectures.

![v540rACBSUepbsQcE4s3PQ_3b799a13034d42938c980d7c473725f1_2SOA6jNuKUowAynp64ms-agTTUcxt1xas4SFTTAcKU-JfqJHyG2vzmM7qgqMh4J_Euwmri_t3G_CUXydGZRlmV4EZABYDusKE7pBnNWi5gZ_fUbiAetmRiQWL3cMO2iRWDtjtAPMazNxnmT-i5pWmPAe (1600×900)](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/v540rACBSUepbsQcE4s3PQ_3b799a13034d42938c980d7c473725f1_2SOA6jNuKUowAynp64ms-agTTUcxt1xas4SFTTAcKU-JfqJHyG2vzmM7qgqMh4J_Euwmri_t3G_CUXydGZRlmV4EZABYDusKE7pBnNWi5gZ_fUbiAetmRiQWL3cMO2iRWDtjtAPMazNxnmT-i5pWmPAe?expiry=1791368528935&hmac=cqjyxq7QkeOVdMAJOhptiyn0OWZnskTJ1lAuRDnCC1s)

## ☁️ Cloud Computing, Hybrid Networks, and Software-Defined Networks

### 🌐 Computing Processes and Cloud Service Models

* **Traditional vs. Cloud:** Traditional networks rely on on-premise physical infrastructure, whereas cloud computing utilizes remote servers, applications, and network services hosted on the internet by a Cloud Service Provider (CSP).
* **Cloud Service Provider (CSP):** Companies owning global data centers with millions of servers that sell storage and computing capabilities through APIs or web consoles.
* **Three Main Service Categories:**
  * **Software as a Service (SaaS):** Remote software suites operated and hosted by the CSP for user consumption.
  * **Infrastructure as a Service (IaaS):** Virtual computer components (virtual containers and storage) configured remotely to operate existing workloads without major modifications.
  * **Platform as a Service (PaaS):** Developer tools used to design and access custom applications for specific business needs.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/oFV1OH67RJOjAed1pXzAuw_6b34b3019d4d448b9c662ebb39970df1_CS_R-042_iass-paas-and-saas.png?expiry=1791368830993&hmac=6elPM7CL9hptdhUZms_CSQVeWPVCRW2dh2Yg_EtI0sA)

### 🔀 Hybrid Cloud Environments and Software-Defined Networks

* **Hybrid Cloud Environment:** Occurs when organizations use a CSP's services alongside their own on-premise computers, networks, and storage (using multiple CSPs is known as a multi-cloud environment).
* **Software-Defined Networks (SDNs):** Composed of virtual network devices and services (such as virtual switches, routers, and firewalls) hosted on servers at CSP data centers, allowing physical hardware to perform packet routing through software.

### 📈 Benefits of Cloud Computing and SDNs

* **Reliability:** High availability of cloud resources, secure connections, and consistent uptime providing minimal operational interruption.
* **Cost Efficiency:** Eliminates heavy upfront infrastructure investments; CSPs offer virtual tools and elastic pricing models at a fraction of the cost of managing physical hardware.
* **Scalability:** Allows companies to scale up or down dynamically using an elastic utility model—paying only for what they need and avoiding the risks of overinvesting in extra hardware.
* **Agility and Security:** Rapid configuration of defensive layers like Web Application Filters (WAFs) or intrusion prevention systems (IDS/IPS) via APIs or web consoles to enhance overall network performance and security.

---

## 🌐 TCP/IP Model vs. OSI Model and Communication Layers

* **Purpose:** Conceptual frameworks (TCP/IP and OSI) that act as guidelines to visualize how hosts communicate, organize data, and transmit it across a network.
* **Troubleshooting Utility:** Help network engineers and security analysts conceptualize network processes and communicate where disruptions or security threats occur.
* **TCP/IP vs. OSI:** The TCP/IP model contains four layers, whereas the OSI model contains seven layers. The TCP/IP model is a simplified version that combines multiple layers of the OSI model.

### 🏗️ The Four Layers of the TCP/IP Model

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/H9jj1YSsSDKlU8c8qzOgsQ_89f77799b50040b08911a8de1012e2f1_CS_R-210_S33G011-edited.png?expiry=1791393813706&hmac=5BGP1DXvOmePZYOTFLtu90VKONlF66itxkwzu-jxx0I)

#### 🔗 1. Network Access Layer

* **Function:** Deals with the creation of data packets and their transmission across a physical network, corresponding directly to physical hardware (hubs, modems, cables, and wiring).
* **Key Protocol:** **Address Resolution Protocol (ARP)**, which maps IP addresses to MAC addresses for local network communication.

#### 🌐 2. Internet Layer

* **Function:** Responsible for ensuring data packets are delivered to destination hosts that may reside on different networks by attaching sender and receiver IP addresses.
* **Key Protocols:**
  * **Internet Protocol (IP):** Routes packets to the correct destination across networks and relies on TCP/UDP for final service delivery.
  * **Internet Control Message Protocol (ICMP):** Shares error information and status updates (such as dropped packets, connectivity issues, and router redirects) for troubleshooting.

#### 📦 3. Transport Layer

* **Function:** Responsible for delivering data between two systems or networks and controlling traffic flow across a network.
* **Key Protocols:**
  * **Transmission Control Protocol (TCP):** A connection-oriented protocol that allows two devices to form a connection, ensures reliable data transmission, retransmits lost or corrupt data, and includes destination port numbers in its header.
  * **User Datagram Protocol (UDP):** A connectionless protocol that does not establish prior connections; used mostly for performance-sensitive, real-time applications (such as video streaming) where delivery tracking is less critical.

#### 🖥️ 4. Application Layer

* **Function:** Corresponds to the application, presentation, and session layers of the OSI model; responsible for making or responding to network requests and defining accessible internet services and applications.
* **Key Protocols:**
  * **Hypertext Transfer Protocol (HTTP)**
  * **Simple Mail Transfer Protocol (SMTP)**
  * **Secure Shell (SSH)**
  * **File Transfer Protocol (FTP)**
  * **Domain Name System (DNS)**

### ⚖️ TCP/IP Model versus OSI Model

* **Conceptual Frameworks:** Both models serve as representative guidelines to help network professionals visualize network processes and protocols regarding data transmission between two or more systems.
* **Structural Differences:** The TCP/IP model contains four layers, whereas the OSI model visually organizes network protocols into seven layers.
* **Model Simplification:** The TCP/IP model is a simplified version that effectively combines multiple layers of the OSI model.
* **Professional Communication:** Network professionals often use the OSI model to communicate about potential sources of problems or security threats when they occur.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/RbNt47PDRTGJZ6q_QtaNMg_9b9098ac04e84c2d8ad04b220c5456f1_CS_R-210_TCP-vs-OSI.png?expiry=1791393813706&hmac=oNygaJxXLnlxn5EanWAadMoWru-fI_poNPJ9PG2vA9U)

* **OSI Model Definition:** A standardized concept consisting of seven layers that describe how computers communicate and send data over a network.
* **Working Direction:** The OSI model is typically analyzed in reverse order—from Layer 7 (application interaction) down to Layer 1 (physical hardware components).
* **Professional Utility:** Network and security professionals utilize both the 4-layer TCP/IP model and the 7-layer OSI model to conceptualize processes, design network standards, and communicate the exact location of disruptions or threats.

### 📑 The Seven Layers of the OSI Model

#### 🖥️ Layer 7: Application Layer

* **Function:** Directly involves everyday users by providing networking protocols that software applications use to connect to the internet through requests.
* **Key Protocols & Examples:** Web browsers using HTTP/HTTPS, email applications using SMTP, and the Domain Name System (DNS) translating domain names into IP addresses.

#### 🔒 Layer 6: Presentation Layer

* **Function:** Handles data translation, compression, and encryption to ensure data formats can be properly interpreted by applications on both sending and receiving systems.
* **Key Example:** Secure Sockets Layer (SSL) encryption operating between web servers and browsers for HTTPS websites.

#### 🔄 Layer 5: Session Layer

* **Function:** Establishes, maintains, keeps open, and terminates communication sessions between two devices.
* **Key Activities:** Manages authentication, reconnection, requests/responses, and setting data transfer checkpoints to resume interrupted transmissions seamlessly.

#### 📦 Layer 4: Transport Layer

* **Function:** Responsible for delivering data between devices, managing data transfer speed and flow, and breaking large transmissions down into smaller segments via **segmentation** for reassembly at the destination.
* **Key Protocols:** Transmission Control Protocol (TCP) and User Datagram Protocol (UDP).

#### 🌐 Layer 3: Network Layer

* **Function:** Oversees receiving frames from the data link layer and delivering them to their intended destination using IP addresses contained within data packets to route them across networks.

#### 🔗 Layer 2: Data Link Layer

* **Function:** Organizes the sending and receiving of data packets within a single local network, housing local network switches and network interface cards.
* **Key Protocols:** Network Control Protocol (NCP), High-Level Data Link Control (HDLC), and Synchronous Data Link Control Protocol (SDLC).

#### 🔌 Layer 1: Physical Layer

* **Function:** Corresponds to the physical hardware involved in network transmission, translating data packets into a stream of 0s and 1s to travel across physical wiring, cables, and devices.
* **Components:** Hubs, modems, cables, and wiring.

## 📦 Network Layer and IPv4/IPv6 Packets

* **Function:** Organizes the addressing and delivery of data packets from host to destination devices across the internet, routing from router to router using destination IP addresses stored in routing tables.
* **IP Packets:** Also referred to as IP packets (TCP) or datagrams (UDP); contain headers with source IP, destination IP, packet size, and protocol information.

### 📄 IPv4 Packet Structure and Header Fields

* **Structure:** Composed of a header (20 to 60 bytes) and a data section (up to 65,535 bytes total).
* **13 Header Fields:**
  * **Version (VER):** Identifies the IP protocol version (e.g., IPv4).
  * **IP Header Length (HLEN/IHL):** Indicates where the header ends and the data begins.
  * **Type of Service (ToS):** Provides packet prioritization for quality of service.
  * **Total Length:** Specifies the entire packet size including header and data.
  * **Identification:** Uniquely identifies fragmented packets for reassembly.
  * **Flags & Fragmentation Offset:** Indicate fragmentation status and placement order within the original packet.
  * **Time to Live (TTL):** Counter decremented by routers to prevent infinite loops; triggers an ICMP error and packet discard when reaching zero.
  * **Protocol:** Specifies the protocol used for the data portion.
  * **Header Checksum:** Detects header corruption in transit.
  * **Source & Destination IP Addresses:** Identify sending and receiving devices.
  * **Options:** Allows additional security/routing options when HLEN exceeds five.

![Diagram of an IPv4 packet header, 13 fields, and bit size](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ZlTJLULmT_-iQusFt5gHLA_34841ae20ac344f4a0248aebe8f0d6f1_CS_R-044_Edited_Pv4-packet-header-14-field.png?expiry=1791394756139&hmac=LspGe34qag0XZUouc_hG83REBu-cYxU6_AksyeW5pn4)

### 🔄 IPv4 versus IPv6 Comparison

* **Exhaustion Mitigation:** IPv6 was developed to combat IPv4 address exhaustion.
* **Address Format & Capacity:**
  * **IPv4:** 4 bytes, four decimal numbers (0–255) separated by periods; allows ~4.3 billion addresses (e.g., `198.51.100.0`).
  * **IPv6:** 16 bytes, eight sets of up to four hexadecimal digits separated by colons; allows 340 undecillion addresses (e.g., `2002:0db8::ff21:0023:1234`).
* **Header Differences:** IPv6 features a simpler header format, omitting fields like IHL, Identification, and Flags, while introducing a **Flow Label** field for special router handling.
* **Security & Routing:** IPv6 provides more efficient routing and eliminates private address collisions common in IPv4.

![Side by side diagrams of an IPv4 packet header and a simplified IPv6 packet](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/PNld6YkmQNWyhZjFFHvC-Q_eb474e5ee3b3416fbc06a639503342f1_CS_R-044_IPv4-and-IPv6.png?expiry=1791394756139&hmac=3DKoQcNQVpBwSQaHVkbqNg8g8nkKC1vaKMVSqIRyi7Q)
