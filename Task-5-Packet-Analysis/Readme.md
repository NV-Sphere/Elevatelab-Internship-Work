## 🎯Task 05: Network Traffic Analysis (Packet Forensics)
## Date: 26 October 2025

### **The Objective:**
The goal was to perform essential packet forensics: capture live network traffic, identify and filter basic communication protocols, and demonstrate the ability to analyze the internal structure of a network
packet using Wireshark.

## Tools:
| Detail | Value | Notes |
| :--- | :--- | :--- |
| **Tool** | **Wireshark (Kali Linux)** | Free, professional network protocol analyzer. |
| **Deliverables** | .pcap file & Protocol Report | Focus on raw data capture and analysis summary. |
| **Traffic Generated** | DNS Lookup, ICMP Ping, and HTTP Browsing | Ensured a mix of essential protocols for analysis. |

---

## Execution and Findings:

### 1. Capture and Protocol Identification
The capture was successfully performed on the active interface (`eth0`/`wlan0`). By applying the filter `dns or icmp or http`, three essential protocols were isolated from the background noise.

### 2. In-Depth Packet Analysis
Analysis was conducted at the protocol stack level to verify communication details:
* **DNS:** Observed the standard query/reply mechanism (Port 53), confirming name resolution process.
* **ICMP:** Captured **Echo Request** and **Echo Reply** packets, validating basic network connectivity.
* **TCP:** Observed packets that would form the **SYN/ACK handshake**, confirming the reliable, connection-oriented nature of web sessions.

### 3. Proof of Stack Analysis
By drilling down into a single ICMP packet, the **full protocol stack** was verified, detailing the Source IP, Destination IP, and internal protocol parameters. This proves the ability to analyze network data at
the **OSI model level**.

--
*(Reference: See the (**proof/**) folder for screenshots of the filtered view , and the (**raw-data/**) folder for the full **.pcap** file and protocol summary.)*

---

## Key Takeaway:

Packet analysis provides **complete transparency** into network activity. This skill is essential in cybersecurity for **troubleshooting, threat hunting, and digital forensics**, as it allows us to see exactly 
what applications are *doing*, rather than just what logs report.

---

## ❓ Interview Questions:

#### 1. What is Wireshark used for?
Wireshark is used for **analyzing network traffic** by capturing and inspecting individual packets. It helps in network troubleshooting, analyzing security vulnerabilities, and developing network protocols.

#### 2. What is a packet?
A packet is the **fundamental unit of data** transmitted over a network. It's a small container that includes the data itself the payload and necessary routing information, such as the source and destination IP 
addresses and port numbers.

#### 3. How to filter packets in Wireshark?
Packets are filtered using **Display Filters** in the filter bar. Examples include filtering by protocol (`http`, `dns`), IP address (`ip.addr == 1.1.1.1`), or port number (`tcp.port == 80`).

#### 4. What is the difference between TCP and UDP?
* **TCP (Transmission Control Protocol):** Is **connection-oriented** and reliable. It establishes a handshake (SYN/ACK) to guarantee that data arrives in order and without errors.
* **UDP (User Datagram Protocol):** Is **connectionless** and unreliable. It is faster but offers no guarantee of delivery or order, making it suitable for video streaming or DNS queries.

#### 5. What is a DNS query packet?
A DNS query packet is a request sent over the network from UDP Port 53) to a DNS server, asking for the **IP address** associated with a specific **domain name** (ex - asking for the IP of `google.com`).

#### 6. How can packet capture help in troubleshooting?
Packet capture helps in troubleshooting by providing a **"ground truth"** view of the network. It allows an analyst to see exactly where a connection is failing (ex - firewall is dropping the SYN packet, 
or the server is sending an error code) and verify the source.

#### 7. What is a protocol?
A protocol is a set of **rules and formats** that define how data should be transmitted, received, and interpreted between two or more devices on a network. It is the common language devices use to communicate
(ex - HTTP is the protocol for web browsing).

#### 8. Can Wireshark decrypt encrypted traffic?
**Generally, no.** Wireshark cannot decrypt traffic encrypted with protocols like **HTTPS/TLS** or **SSH** unless the analyst holds the **private key** of the server. For public analysis, the encrypted payload
remains unreadable.

---
