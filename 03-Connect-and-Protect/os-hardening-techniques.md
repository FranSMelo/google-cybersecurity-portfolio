
# Cybersecurity Incident Report: Compromised Web Application & Brute Force Investigation

## 1. Exercise Overview & Scenario Description

* **Context:** You operate as a cybersecurity analyst for `yummyrecipesforme.com`, an e-commerce and content platform specializing in recipes and cookbooks.
* **Incident Description:** Multiple end-users and customers contacted the technical support helpdesk reporting abnormal behavior when attempting to access the company website. Specifically, visitors were immediately confronted with an unauthorized prompt demanding the download of an executable file. Upon execution, victims experienced performance degradation on their personal systems alongside forced browser redirections to an external, malicious domain (`greatrecipesforme.com`).
* **Investigation Scope & Initial Findings:** Upon attempting to access the administrative dashboard, the web site owner discovered active credential revocation, indicating a complete administrative lock-out. An exhaustive forensic investigation conducted by the security team—integrating isolated sandbox environment emulation, packet capture analysis via `tcpdump`, and application source code auditing—revealed that a disgruntled former employee compromised the web hosting infrastructure via an unmitigated brute-force attack against default administrative credentials. Following successful authentication, the threat actor manipulated the source code to inject malicious JavaScript, facilitating malware distribution and traffic redirection.

---

## 2. Incident Report Resolution & Technical Analysis

### Section 1: Identify the Network Protocol Involved in the Incident

* **Detailed Network Protocol Breakdown:** Based on the captured `tcpdump` traffic log, two core protocol suites operating across different layers of the TCP/IP model were fundamentally involved in the attack lifecycle:
  1. **DNS (Domain Name System) over UDP Port 53:** Utilized during the initial phase to query recursive name servers (`dns.google.domain`) for the translation of human-readable domain names (`yummyrecipesforme.com` and `greatrecipesforme.com`) into routable IPv4 addresses via A-record lookups. DNS operates primarily on UDP due to its lightweight and fast transaction model, though its lack of inherent authentication leaves it susceptible to spoofing if proper controls are absent.
  2. **HTTP (Hypertext Transfer Protocol) over TCP Port 80:** Responsible for application-layer communications between the client machine and the web servers. The logs indicate standard TCP three-way handshakes followed by HTTP GET requests (`GET / HTTP/1.1`). Because standard HTTP transmits data in cleartext without encryption, it allowed the injected malicious JavaScript payload and subsequent file downloads to be transmitted directly to visiting browsers.

### Section 2: Document the Incident & Traffic Log Forensic Analysis

* **Chronological Incident Timeline & Root Cause Analysis:**

  * **Exploit Vector & Initial Access:** The threat actor exploited weak administrative configurations by executing an automated brute-force attack against the web application's management login portal. Due to the absence of account lockout thresholds, rate-limiting, and non-default password policies, the attacker successfully guessed default administrative credentials.
  * **Persistence & Malicious Modification:** Having attained administrative privileges, the attacker altered the application source code to insert malicious JavaScript payloads. This script dynamically generated an automated download prompt disguised as a critical browser security update whenever a user requested the homepage.
  * **Redirection & Payload Delivery:** Executing the downloaded file compromised the victim's endpoint, causing CPU/memory spikes and executing a secondary redirection sequence pointing users toward the attacker-controlled server (`greatrecipesforme.com`). To maintain unauthorized exclusivity, the attacker modified the administrative password, preventing internal staff from accessing the control panel.
* **Granular `tcpdump` Traffic Log Analysis & Evidence:**
  The diagnostic network capture recorded inside the sandbox environment details the exact transactional sequence of the compromise:

  1. **Legitimate Site Name Resolution:**

     ```text
     14:18:32.192571 IP your.machine.52444 > dns.google.domain: 35084+ A? yummyrecipesforme.com. (24)
     14:18:32.204388 IP dns.google.domain > your.machine.52444: 35084 1/0/0 A 203.0.113.22 (40)
     ```

     * *Forensic Interpretation:* The client queries Google's public DNS resolver for `yummyrecipesforme.com` and successfully receives the legitimate hosting server's IPv4 address (`203.0.113.22`).
  2. **Initial Web Connection & Malware Exposure:**

     ```text
     14:18:36.786501 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [S], ...
     14:18:36.786589 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, length 73: HTTP: GET / HTTP/1.1
     ```

     * *Forensic Interpretation:* Following a standard TCP handshake, the browser transmits an HTTP GET request to port 80. The response served back contains the compromised source code, immediately triggering the fraudulent download prompt.
  3. **Malicious Domain Resolution and Redirection Phase:**

     ```text
     14:20:32.192571 IP your.machine.52444 > dns.google.domain: 21899+ A? greatrecipesforme.com. (24)
     14:20:32.204388 IP dns.google.domain > your.machine.52444: 21899 1/0/0 A 192.0.2.17 (40)
     14:25:29.576590 IP your.machine.56378 > greatrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, length 73: HTTP: GET / HTTP/1.1
     ```

     * *Forensic Interpretation:* After execution of the malicious payload, the infected client machine performs a new DNS lookup for the attacker's infrastructure (`greatrecipesforme.com`, resolving to `192.0.2.17`) and establishes an HTTP session, confirming complete browser hijacking and malware staging.
* **Evidence & Verification Sources:** Incident findings are fully corroborated by customer helpdesk escalation logs, controlled sandbox network captures (`tcpdump`), and static code analysis reports identifying unauthorized script injection.

### Section 3: Recommend Comprehensive Remediation for Brute-Force Attacks

* **Selected Remediation Strategy:** Implementation of Mandatory Multi-Factor Authentication (MFA/2FA), Dynamic Account Lockout Policies, and Strict Password Complexity Standards.
  * *Two-Factor Authentication (2FA):* Eliminates single-point-of-failure authentication. Even if an attacker successfully executes a dictionary or brute-force attack to guess a user's password, access is denied without a secondary, dynamic verification factor (such as TOTP authenticator apps or hardware keys).
  * *Account Lockout & Rate Limiting:* Configuring web application firewalls (WAF) and server authentication modules to temporarily lock accounts or impose exponential delays after 3 to 5 consecutive failed login attempts effectively neutralizes automated script-based brute-force enumeration.
  * *Mandatory Credential Hygiene:* Enforcing strict password policies that prohibit default credentials upon deployment and require periodic rotation ensures that administrative portals are resistant to credential-stuffing and brute-force vectors.
