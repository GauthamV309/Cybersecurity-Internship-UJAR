# 🛡️ Web Vulnerability Assessment Report

This project contains a detailed vulnerability assessment report generated after scanning a deliberately vulnerable web application (DVWA) hosted locally at `http://127.0.0.1:8000`. The scan simulates real-world application testing using **OWASP ZAP v2.14.0**.


---

## 📋 Report Summary

- **Target Application:** DVWA (Damn Vulnerable Web Application)
- **Tool Used:** OWASP ZAP (Full Active Scan)
- **Scan Date:** August 15, 2025
- **Report Format:** HTML (`vulnerability-report.html`)
- **Total Issues Found:** 12
  - 🟥 3 Critical/High
  - 🟧 4 Medium
  - 🟦 5 Low

---

## 🔍 Top Vulnerabilities Identified

| # | Vulnerability                    | Severity  | OWASP Top 10 |
|---|----------------------------------|-----------|---------------|
| 1 | SQL Injection                    | Critical  | A03:2021      |
| 2 | Reflected Cross-Site Scripting   | High      | A03:2021      |
| 3 | Insecure Direct Object Reference | High      | A01:2021      |
| 4 | Missing HTTP Security Headers    | Medium    | A05:2021      |
| 5 | Plaintext Password Transmission  | Medium    | A02:2021      |

Each finding includes:
- CWE & OWASP references  
- PoC payloads and HTTP snippets  
- CVSS v3.1 severity scores  
- Remediation steps and best practices

---

## 📁 Files Included

- `vulnerability-report.html` — Full formatted report with interactive styling
- `README.md` — This file, describing the report context

---

## 🖥️ How to View the Report

1. Clone or download this repository.
2. Open `vulnerability-report.html` in any modern web browser.

---

## 🧪 Tools & Environment

- **Scan Tool:** OWASP ZAP v2.14.0  
- **Test App:** DVWA running on `localhost:8000`  
- **Environment:** Local VM (Kali Linux)

---

## 🧠 Purpose of This Project

This project was created for:
- Practicing automated web vulnerability scanning
- Demonstrating report writing for web application security
- Showcasing knowledge of OWASP Top 10 vulnerabilities
- Building a cybersecurity portfolio

---

