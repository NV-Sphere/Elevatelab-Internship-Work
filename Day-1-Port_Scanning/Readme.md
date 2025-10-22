#🎯Day 01 Task: Scan Your Local Network for Open Ports
Date: 22 October 2025

# The Task Brief
Today's crucial task was to perform an ethical intrusion simulation. I acted as a scanner to assess my local network's security posture, using stealthy techniques 
and traffic analysis to find open ports and understand my digital exposure.

#🔧 Tools we use 
* Kali Linux: My platform for ethical hacking.
* Nmap (The Network Mapper): Used the stealthy half-open scan (-sS)—a gentle knock on the door—to identify services.
* Wireshark (The Network Packets Listener): Used to  validate the scan by observing the TCP SYN packets and confirming the protocol in action.

# What I Found: A Secure Neighbourhood🏠

# The Scan:
I targeted the local subnet (`192.168.220.0/24`) for the first 1000 common ports. The Nmap scan and Wireshark capture were completed successfully.

### **Key Findings:**
1.  Open Ports: Only one host (`192.168.220.0`) showed an open port: (Port 53 (DNS/Domain)). And it's a necessary port  for internet traffic (router/DNS server),
not harmful.
2. Firewall Protection: The majority of other active hosts showed "filtered" ports. This is good security✅; it means a dedicated "firewall"
4.   is actively dropping my scan packets, ignoring the probes rather than responding "closed." This reflects a smart defensive mechanism.

---->   **(Reference: See the (proof/) folder for screenshots and (raw-data/) for the Nmap output file.)** <----------
___________________________________________________________________________________________________________________________________________________________________
#❔Interview Questions:

The biggest learning was the critical difference between **CLOSED** (sends RST) and **FILTERED** (sends no response due to firewall) ports. This distinction
is vital for accurate security assessment and understanding the target's defensive strategy.

1. What is an open port?
An open port represents a running service on a device/host that is actively managing the task on an OS. When a port is open, a specific service is running
on that port like (HTTP, SSH, DNS, TELNET), Every service is connected to that port number and is configured to accept incoming connections.  From 
An external perspective, an open port is a clear indicator of an active service.

2. How does Nmap perform a TCP SYN scan?
A TCP SYN scan works by sending a *SYN* (synchronise) packet to the target port. If the port is open, the target replies with a (SYN/ACK) packet. Nmap then
immediately sends an *RST* (reset) packet instead of the final ACK, preventing a full connection from being established. This makes it faster and efficient.

3. What risks are associated with open ports?
Open ports introduce a direct attack surface proportional to the number of ports open. The risks are substantial: Vulnerability Exposure (Ex, outdated software can
be exploited), Misconfiguration (Ex: weak default settings offering unauthorised access), and excessive Information Gathering, where an attacker can easily do
reconnaissance 

4. Explain the difference between TCP and UDP scanning.
TCP scanning uses the connection-oriented nature of TCP; it focuses  on the reliable three-way handshake to confirm a port's status (open/closed).
UDP scanning targets the connectionless UDP protocol. Since there is no handshake, determining port status is harder
Nmap relies on the host sending an ICMP Port Unreachable  message to confirm a port is closed. If no message is received, the port is chosen, labelled "open|filtered",
making UDP scans slower and less useful.

5. How can open ports be secured?
Open ports are secured through a strategy known as "least privilege" by "Restricting Access" (use Firewalls that only allow specific source IP addresses).
Closing Unnecessary Ports and keeping the running services fully patched and updated.

6. What is a firewall's role regarding ports?
A firewall acts as a gatekeeper. Its primary role regarding ports is to Filter Traffic, determining which packets are allowed (accepted) or blocked (denied) based
on source, destination, and port number. It can also mask services by making ports appear "filtered" for external scanners.

7. What is a port scan, and why do attackers perform it?
A port scan is the act of systematically checking a server or host for open ports. Attackers perform it for reconnaissance, which is the first step in a
cyber attack chain. The goal is to Identify Services and quickly spot weak points or vulnerable services that can be exploited for initial access, and get privileges.

8. How does Wireshark complement port scanning?
Wireshark provides validation and deeper insight. It complements port scanning by allowing the security professional to observe the raw packets coming to the network
(SYN, SYN/ACK, RST) sent and received, confirming the scanner (Nmap) worked as expected. This helps in troubleshooting and understanding the underlying TCP/IP
protocol stack in action.
