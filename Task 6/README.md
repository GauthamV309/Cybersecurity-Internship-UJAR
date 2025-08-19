Thanks! Based on your detailed **Mini Guide** and the context, here's a concise **student-style lab report** or **task write-up** following those instructions. You can use or adapt it for documentation, assignments, or training material.

---

# 🔬 **Mini Lab Report: Traffic Sniffing Using Wireshark**

**Name**: \[Your Name]
**Date**: August 19, 2025
**OS Used**: Windows 11 / Linux Ubuntu 22.04
**Tool**: Wireshark v4.x
**Network Interface Used**: Wi-Fi (wlan0) / Ethernet (eth0)

---

## ✅ Task Objective

To observe and analyze real-time network traffic on a local machine using Wireshark, applying filters to identify protocols and detect basic network behavior, including secure vs insecure transmissions.

---

## 🛠️ Steps Performed

### 1. **Installation**

* Installed **Wireshark** via the official website / `apt install wireshark`.

### 2. **Run as Administrator**

* Launched Wireshark with elevated permissions to allow full packet capture.

### 3. **Interface Selection**

* Selected the **active network interface** (Wi-Fi).

### 4. **Capture Start**

* Started live packet capture.

### 5. **Traffic Generation**

* Opened a browser and visited:

  * `http://example.com`
  * `https://www.google.com`
* Opened terminal/command prompt and ran:

  * `ping google.com`
  * Downloaded a small file using curl or wget

### 6. **Stop Capture**

* Stopped the capture after \~2 minutes.

### 7. **Applied Filters**

* Used various **Wireshark filters**:

  * `http`
  * `dns`
  * `icmp`
  * `tcp.port == 443`
  * `ip.addr == [my IP]`
  * `tcp.flags.syn == 1`

---

## 🔍 Observations

### ◾ DNS

* DNS queries were sent to resolve domain names.
* Observed `A` and `AAAA` record requests and responses.

### ◾ HTTP vs HTTPS

* Traffic to `http://example.com` was visible in **plain text** (`http`).
* Traffic to `https://www.google.com` was **encrypted** (`tls`).

### ◾ ICMP

* Ping to `google.com` resulted in visible **ICMP Echo Request/Reply** packets.

### ◾ TCP 3-Way Handshake

* Observed handshake: SYN → SYN-ACK → ACK for HTTPS connections.

### ◾ Protocol Stack

* Each packet followed the typical stack:

  * Ethernet > IP > TCP/UDP > Application Layer (DNS/HTTP/etc.)

---

## 🧠 Learning Outcomes

* Gained hands-on experience with **packet sniffing** and Wireshark usage.
* Learned to use **filters** to isolate specific protocol traffic.
* Understood the **structure of packets** and **how data flows** over the network.
* Differentiated between **encrypted (HTTPS)** and **unencrypted (HTTP)** traffic.
* Identified basic indicators of **insecure communication** (e.g., visible login forms in HTTP).

---

## 🧪 Key Concepts Observed

| Concept | Observation                                                 |
| ------- | ----------------------------------------------------------- |
| ARP     | ARP broadcast requests were visible at the start of capture |
| DNS     | Queries for domains like `example.com`, `google.com`        |
| ICMP    | Clear echo requests and replies during ping                 |
| TCP     | Handshake, flags (SYN, ACK), sequence numbers               |
| HTTP    | Plain text requests (only over non-HTTPS)                   |
| TLS     | Handshake observed for secure traffic, with SNI             |

---

## 📂 Files Saved

* Capture File: `lab_sniffing_capture.pcapng`
* Notes File: `protocol_observations.txt`

---

## 🚩 Indicators of Insecure Communication

* HTTP requests sent in **clear text** — could be intercepted.
* DNS queries were **unencrypted**.
* No signs of clear-text credentials observed, but this could occur in non-HTTPS login forms.

---

## 📘 Filters Used

| Filter               | Purpose                           |
| -------------------- | --------------------------------- |
| `http`               | View HTTP requests and responses  |
| `dns`                | View domain lookups               |
| `icmp`               | See ping traffic                  |
| `tcp.port == 443`    | Show HTTPS (encrypted) traffic    |
| `ip.addr == YOUR_IP` | Focus on your machine’s traffic   |
| `tcp.flags.syn == 1` | Detect TCP connection initiations |

---

