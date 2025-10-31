# 🎯Task 08: Working with VPNs

## Date: 31 October 2025

### The Objective:
The goal was to **understand the role of VPNs in protecting privacy and secure communication** by configuring, connecting, and verifying the effects of a VPN connection on IP address and network speed.

## Execution Summary:
| Detail | Value | Notes |
| :--- | :--- | :--- |
| **Tool Used** | **Windscribe (Free Tier)** | Desktop application used for full system encryption. |
| **Target Verified** | IP Address Change | Verified change from India (Original IP) to **USA (23.94.48.123)**. |
| **Testing Methods** | **Ping, Traffic Flow, Web Search** | Performed latency check (Ping) and confirmed encrypted browsing (Netflix). |
| **Latency Impact** | **+247 ms Added** | Latency increased from **33.8 ms (OFF)** to **280.8 ms (ON)**, validating the encryption overhead and physical distance. |

---

## Privacy and Encryption:

### 1. Proof of Secure Tunnel (IP Spoofing)
The task demonstrated the core function of a VPN: protecting privacy by **spoofing the user's geographic location** and **masking the true IP address**. This is vital when using public Wi-Fi or sensitive browsing.

### 2. Encryption and Protocol Verification
Traffic flowing through Windscribe uses robust protocols like **WireGuard (ChaCha20)** or **OpenVPN (AES-256-GCM)**. The successful browsing tests (**Netflix/Web Search**) confirm that all outbound traffic is successfully summarised
and **encrypted (HTTPS)**, preventing the ISP or network observers from inspecting the data content.

### 3. Key Research Findings (No-Logs Policy)
Windscribe adheres to a **strict No-Logs Policy**. They do not store connection logs, session logs, or IP timestamps that can personally identify a user. This guarantees that user activity remains confidential and cannot be handed over
to third parties.

*(Reference: See the **(proof/)** folder for screenshots of the VPN analysis , and the **(raw-data/)** folder for the **latency comparison and research log**.)*

---

## ❓Interview Questions:

#### 1. What is a VPN?
A VPN (Virtual Private Network) is a service that creates a **secure, encrypted tunnel** for your internet connection. It routes your traffic through a server operated by the VPN provider, masking your real IP address and encrypting
your data as it travels online.

#### 2. How does a VPN protect privacy?
A VPN protects privacy primarily by:
1.  **Masking IP:** Hiding your true IP address, making your location anonymous.
2.  **Encryption:** Scrambling your data (traffic) so that your ISP, government, or hackers cannot read what you are doing.

#### 3. Difference between VPN and proxy?
| Feature | VPN | Proxy Server |
| :--- | :--- | :--- |
| **Encryption** | **Encrypts** all traffic (secure tunnel) | **No encryption** (Data is often sent in plain text). |
| **Coverage** | **Encrypts entire device** (all apps) | **Encrypts only browser** traffic (or the specific app configured). |

#### 4. What is encryption in VPN?
Encryption in a VPN is the process of converting readable user data (plain text) into an **unreadable code (ciphertext)** using algorithms like **AES-256**. This ensures that even if traffic is intercepted within the VPN tunnel, the data 
content remains confidential and cannot be understood.

#### 5. Can VPN guarantee complete anonymity?
**No.** A VPN provides **strong privacy** by masking your IP and encrypting traffic, but it cannot guarantee **complete anonymity**. Your actions can still be traced by: logging activity on the VPN server itself (if the provider is 
dishonest) or through digital footprints like browser cookies and login data.

#### 6. What protocols do VPNs use?
Modern VPNs use robust protocols like **WireGuard** (known for its speed and simplicity) and **OpenVPN** (known for its security and stability). Older protocols like PPTP or L2TP are now considered less secure.

#### 7. What are some VPN limitations?
VPN limitations include:
1.  **Reduced Speed:** Encryption and routing traffic over long distances increase latency (ping) and can reduce connection speed.
2.  **Trust:** Security depends on the **VPN provider's honesty** (their "no-logs" claim).
3.  **Cost:** Free VPNs often have bandwidth limits or slow speeds.

#### 8. How does a VPN affect network speed?
A VPN generally **reduces** network speed and **increases latency (ping)**. This is because every packet must be encrypted, encapsulated, sent through the VPN server, and then decrypted at the destination, adding processing time and 
distance to the route.

---
