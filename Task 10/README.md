# 🔒 Cybersecurity Internship – Phase 1  
## Task 10: Creating a Firewall with iptables or UFW  
**Date Completed:** August 26, 2025  
**Platform:** Ubuntu 22.04 (Linux)  
**Tool Used:** UFW (Uncomplicated Firewall)  

---

## 🎯 Objective

The objective of this task was to learn how to configure a basic **host-based firewall** using UFW (Uncomplicated Firewall). This involved creating, managing, and inspecting rules to **control inbound and outbound traffic** based on IP addresses, ports, and protocols, which is critical for securing Linux systems.

---

## 🛠️ Tools & Setup

- **Operating System:** Ubuntu 22.04  
- **Firewall Tool:** UFW  
- **Access Level:** Root or sudo privileges  

---

## 🧪 Procedure

### 1. 🔧 Install and Enable UFW:
```bash
sudo apt install ufw
sudo ufw enable
2. 🔐 Set Default Policies:
Deny all incoming traffic.

Allow all outgoing traffic.

bash
Copy code
sudo ufw default deny incoming
sudo ufw default allow outgoing
3. ✅ Allow Specific Services:
Allow SSH for remote administration:

bash
Copy code
sudo ufw allow ssh
Allow HTTP (port 80) for web access:

bash
Copy code
sudo ufw allow 80/tcp
Allow HTTPS (port 443) for secure web traffic (optional):

bash
Copy code
sudo ufw allow 443/tcp
4. 🚫 Block a Suspicious IP:
Block traffic from an example IP address (e.g., a suspected malicious actor):

bash
Copy code
sudo ufw deny from 192.168.1.50
5. 🔍 Check UFW Status:
To view all active rules and verify the firewall state:

bash
Copy code
sudo ufw status verbose
📊 Findings
Default rules (deny incoming, allow outgoing) were successfully applied.

SSH, HTTP, and HTTPS ports were allowed as configured.

Suspicious IP (192.168.1.50) was successfully blocked.

All rules persisted across system reboots.

UFW's interface simplified firewall management while retaining advanced control.
