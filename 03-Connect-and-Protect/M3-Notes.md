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
