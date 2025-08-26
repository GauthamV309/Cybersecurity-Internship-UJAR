# 🛡️ Cybersecurity Internship – Phase 1  
## Task 7: Website Directory Bruteforcing Using Dirb or Gobuster  
**Date Completed:** August 26, 2025  
**Target Site:** [http://testphp.vulnweb.com](http://testphp.vulnweb.com)  
**Tools Used:** Kali Linux, Dirb, Gobuster, SecLists Wordlist  

---

## 🎯 Objective

The objective of this task was to perform **directory and file enumeration** on a target website using `Dirb` and `Gobuster`. The goal was to identify hidden or unlisted directories such as admin panels, backups, or misconfigured paths that could potentially expose sensitive information. This task mimics real-world reconnaissance methods used during ethical hacking engagements.

---

## 🛠️ Setup & Execution

### 🔹 Environment:
- **Operating System:** Kali Linux  
- **Target:** http://testphp.vulnweb.com  
- **Wordlist:** `/usr/share/wordlists/dirb/common.txt` (SecLists available but not required)

### 🔹 Commands Used:

#### ✅ Dirb:
```bash
dirb http://testphp.vulnweb.com /usr/share/wordlists/dirb/common.txt
✅ Gobuster:
bash
Copy code
gobuster dir -u http://testphp.vulnweb.com -w /usr/share/wordlists/dirb/common.txt
Scan Mode: Basic directory scan (non-recursive)

No file extension scanning (e.g., .php) used for initial sweep.

🔍 Findings
📂 Discovered Directories:
/admin/ – Accessible; may expose admin panel

/backup/ – 301 redirect; possible backup location

/config/ – 403 Forbidden; likely contains sensitive configs

/uploads/ – Accessible; possible file upload vulnerability

/test/ – Possibly unused development directory

🔢 HTTP Status Codes Observed:
200 OK – Directory exists and is accessible

301 Moved Permanently – Redirected resource

403 Forbidden – Restricted resource, possible sensitive content

404 Not Found – Non-existent directory (e.g., /uploads/secret/)

📈 Analysis
✔️ Wordlist Efficiency:
The common.txt wordlist successfully identified standard and common paths.

For deeper reconnaissance, custom or larger wordlists (from SecLists) could reveal more obscure paths.

✔️ Rate Limiting:
No rate limiting or bot protection was detected.

Scanning was throttled manually to mimic normal user behavior and avoid detection.

✔️ Ethical Scope:
All scans were performed on a legal, intentionally vulnerable website designed for testing (VulnWeb).

Unauthorized scanning of live, production, or private websites is strictly prohibited without explicit permission.
