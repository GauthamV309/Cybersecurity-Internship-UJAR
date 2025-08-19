# 🔍 Directory Bruteforcing Report

## 📁 Overview

This report documents the process and results of directory bruteforcing against a locally hosted web server using tools like **Dirb** and **Gobuster**. The purpose was to identify hidden or sensitive paths that are not directly linked from the main page.

---

## ✅ Environment Setup

- **Operating System**: Kali Linux
- **Web Server**: Python HTTP server on port `8000`
- **Command**:
  ```bash
  python3 -m http.server 8000

Files in Web Root:

index.html

admin/

config.php

.hidden/


