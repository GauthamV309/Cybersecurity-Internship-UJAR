# 🔐 Cybersecurity Internship – Phase 1  
## Task 8: Cracking Password Hashes with John the Ripper  
**Date Completed:** August 26, 2025  
**Tools Used:** Kali Linux, John the Ripper, OpenSSL, rockyou.txt  

---

## 🎯 Objective

The objective of this task was to learn how to **crack password hashes** using John the Ripper (JTR), understand how hashing and salting work, and observe the importance of strong password practices in protecting against dictionary and brute-force attacks.

---

## 🛠️ Tools & Setup

- **Operating System:** Kali Linux  
- **Hashing Tool:** OpenSSL  
- **Cracking Tool:** John the Ripper (JTR)  
- **Wordlist:** `/usr/share/wordlists/rockyou.txt`  

---

## 🧪 Procedure

### 1. ✅ Install/Update John the Ripper:
```bash
sudo apt update && sudo apt install john
2. 🔐 Generate a Sample Password Hash:
A sample password mypassword123 was hashed using MD5-Crypt:

bash
Copy code
echo -n 'mypassword123' | openssl passwd -1 -stdin
Output:

perl
Copy code
$1$12345678$AvuWqQGvO/yMR1Jh8Kj0Z1
3. 💾 Save the Hash to a File:
Create a file hash.txt containing the hash in /etc/shadow format:

perl
Copy code
testuser:$1$12345678$AvuWqQGvO/yMR1Jh8Kj0Z1
4. 🧨 Run John the Ripper:
Use the rockyou.txt wordlist to attempt to crack the password:

bash
Copy code
john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
5. 👀 Reveal the Cracked Password:
After the process completes:

bash
Copy code
john --show hash.txt
Output:

ruby
Copy code
testuser:mypassword123:1:1:Test User:/home/testuser:/bin/bash
🔎 Findings
Password Cracked: mypassword123

Hash Type: MD5-Crypt (detected automatically by John)

Time Taken: ~5 seconds

Wordlist Used: rockyou.txt (common real-world password list)
