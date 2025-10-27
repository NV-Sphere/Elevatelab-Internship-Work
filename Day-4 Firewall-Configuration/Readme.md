## 🎯Day 04 Task: Configuring and Testing Firewall Rules

## Date: 25 October 2025

### My Approach and Strategy:

The objective was to configure and test firewall rules. Although the task mentioned UFW (Linux CLI), I chose the **Windows Defender Firewall (GUI)** for this submission.

### Why Windows Firewall?
I chose the GUI method primarily for **better documentation and clear understanding**. Using the Windows Firewall GUI allows for **high-quality, clean screenshots** of the rule creation and activation,
which is essential for a professional report. While UFW on Linux is often considered cooler, the GUI provides far better visual proof and better understanding of security concepts and for the raw
terminal output. 
(I am also familiar with the complex RDP 3389 port, but chose SSH 22 for better compliance.)

## Firewall Rule Execution & Proof:

| Detail | Value | Notes |
| :--- | :--- | :--- |
| Tool Used | Windows Defender Firewall (GUI) | Best for visual proof |
| Testing Tool | PowerShell (`Test-NetConnection`) | Used to validate rule effectiveness. |
| Target Port | TCP 23 (Telnet) | **DENY** rule created. |
| Allowed Port | TCP 22 (SSH) | **ALLOW** rule created. |

### Execution Steps:

1.  **Rule Blocked (Port 23):** A new inbound rule was created to **Block the connection** on TCP Port 23.
2.  **Test Result:** The rule was tested using PowerShell, which showed **`TcpTestSucceeded : False`**. This proved the firewall successfully dropped the connection.
3.  **Allow Rule Added (Port 22):** A second inbound rule was added to **Allow the connection** on TCP Port 22 (SSH), demonstrating the explicit permit action.

*(Reference: See `proof/test_block_failed.png` showing the failed test.)*  

### Cleanup:

The test block rule (`BLOCK_TELNET23`) was **deleted** to restore the system state. The Port 22 Allow rule was intentionally left active to showcase the final configuration state.

*(Reference: See `proof/cleanup_complete.png` showing the final rules list.)*

---

## Security Summary:

A firewall acts as a digital traffic police, managing all incoming and outgoing network traffic based on its rules. It inspects every incoming packet, specifically looking at the **Port Number**.
If the packet matches a configured DENY rule (like our Port 23 block), the firewall silently drops the packet. If it matches an ALLOW rule (like our Port 22 rule), the packet is permitted to reach the
target application.

---

## ❓Interview Questions: Firewall Management

#### 1. What is a firewall?
A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on security rules. It acts as a barrier between a trusted internal network and untrusted external 
networks.

#### 2. Difference between stateful and stateless firewall?
* **Stateless Firewall:** Inspects each network packet individually, without considering its context or history with previous packets. It is fast but cannot identify complex attacks.
* **Stateful Firewall:** Tracks the status of active network connections. It only allows response traffic that is part of an existing, approved connection, making it much more secure and effective against modern
threats.

#### 3. What are inbound and outbound rules?
* **Inbound Rules:** Control traffic coming *into* your computer (from the internet to your machine). Used to block attacks or unwanted access.
* **Outbound Rules:** Control traffic going *out* of your computer (from your machine to the internet). Used to prevent malware from leaking data.

#### 4. How does UFW simplify firewall management?
UFW (Uncomplicated Firewall) simplifies management by providing a simple, user-friendly command-line interface (CLI) that translates easy instructions (like `ufw deny 23`) into the complex rules required by the
underlying Linux kernel firewall.

#### 5. Why block port 23 (Telnet)?
Port 23 (Telnet) is blocked because the Telnet protocol transmits all data, including **login credentials**, in plain, unencrypted text. This makes it extremely vulnerable to eavesdropping attacks. Blocking it
forces users to use secure alternatives like SSH (Port 22).

#### 6. What are common firewall mistakes?
Common mistakes include **leaving unused ports open** (creating unnecessary attack surfaces), using overly **broad allow rules** , allowing access from `ANY` source IP, and failing to update the firewall with
**new security policies** when new applications are installed.

#### 7. How does a firewall improve network security?
A firewall improves security by **reducing the attack surface**. By enforcing a strict policy of "deny all, permit," it prevents unauthorised access to vulnerable services, blocks dangerous traffic, and monitors 
activity.

#### 8. What is NAT in firewalls?
NAT (Network Address Translation) is a function often performed by boundary firewalls or routers. It translates a single, private internal IP address like your PC's local IP into a single, public external IP
address, allowing multiple internal devices to share one public connection, which helps hide the internal network.

---
