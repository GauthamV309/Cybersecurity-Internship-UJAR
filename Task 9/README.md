# 🕵️‍♂️ Cybersecurity Internship – Phase 1  
## Task 9: Man-in-the-Middle (MITM) Attack Using Ettercap  
**Date Completed:** August 26, 2025  
**Target Environment:** Local Virtual Network (Kali Linux + Ubuntu VM)  
**Tools Used:** Ettercap (GUI), Kali Linux, Wireshark (optional)

---

## 🎯 Objective

This task focused on performing a **Man-in-the-Middle (MITM)** attack via **ARP spoofing** using Ettercap. The goal was to intercept and analyze network traffic between two devices, simulating a real-world attack scenario. This exercise demonstrates the risks of unencrypted traffic and emphasizes the importance of secure communication protocols such as **HTTPS, SSL/TLS, and VPNs**.

---

## 🛠️ Environment & Tools

- **Attacker:** Kali Linux (VirtualBox VM)  
- **Victim:** Ubuntu 20.04 (VirtualBox VM)  
- **Network:** VirtualBox internal network (LAN simulation)  
- **Tools:**  
  - Ettercap (Graphical Interface)  
  - Wireshark (for optional packet inspection)  

---

## 🧪 Setup & Procedure

### 1. 🧱 Environment Setup:
- Both Kali and Ubuntu VMs were connected to an internal network in VirtualBox to simulate a local LAN.
- Attacker's IP: *Kali Linux VM*  
- Victim's IP: *Ubuntu VM*  
- Gateway: VirtualBox NAT adapter

### 2. 🔧 Enable IP Forwarding:
To ensure traffic is correctly routed through the attacker:
```bash
echo 1 > /proc/sys/net/ipv4/ip_forward
3. 🚀 Launch Ettercap GUI:
Start Ettercap with root privileges in graphical mode:

bash
Copy code
sudo ettercap -G
4. 📡 Network Sniffing Setup:
Select Unified Sniffing and choose the correct network interface (eth0).

Perform a host scan to detect connected devices.

From Hosts List, select:

Target 1: Victim's IP (Ubuntu)

Target 2: Gateway IP (NAT Adapter)

5. 🧨 Initiate ARP Spoofing:
Navigate to MITM > ARP Poisoning

Enable “Sniff remote connections”

Start MITM attack

6. 🔍 Begin Sniffing:
Start the sniffing session

Monitor traffic between victim and gateway

Open http://neverssl.com on the victim machine to generate HTTP traffic

Optional: Use Wireshark to inspect packets in detail

📊 Findings
Successfully intercepted unencrypted HTTP traffic between the victim and the gateway.

Captured a plaintext username and password in an HTTP POST request.

HTTPS traffic was present but not viewable due to encryption (SSL/TLS).

Verified the intercepted packets using Wireshark for packet-level inspection.

📘 Learning Outcomes
Understood how ARP spoofing redirects traffic through the attacker.

Observed how vulnerable HTTP communication is to eavesdropping.

Learned the role of IP forwarding in keeping the MITM attack seamless.

Saw the limitations of interception when encryption (HTTPS) is used.

Gained insight into how Wireshark supports MITM attack analysis.

⚠️ Ethical Considerations
This task was executed in a controlled lab environment using virtual machines.

MITM attacks are illegal without explicit authorization.

These techniques must only be used for ethical hacking, penetration testing, or academic learning with proper consent.

