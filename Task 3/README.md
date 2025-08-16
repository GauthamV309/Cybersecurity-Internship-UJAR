# HTTP Security Header Analysis – Key Findings and Summary

## Overview

This project involved analyzing the HTTP response headers of three websites:
- https://www.wexinc.com/
- https://www.box.com/
- https://chatgpt.com/

The goal was to evaluate the presence and configuration of critical HTTP security headers, understand their protective roles, and identify improvement areas to harden each site's web security posture.

---

## Key Security Headers Reviewed

| Header Name               | Purpose                                                                 |
|---------------------------|-------------------------------------------------------------------------|
| Content-Security-Policy   | Mitigates XSS by restricting the sources of content loaded by the browser |
| X-Frame-Options           | Prevents clickjacking by disallowing the site to be framed              |
| Strict-Transport-Security | Enforces HTTPS and prevents protocol downgrade attacks                 |
| X-Content-Type-Options    | Prevents MIME-type sniffing by the browser                             |
| Referrer-Policy           | Controls the amount of referrer information shared                     |
| Permissions-Policy        | Restricts access to browser features and APIs                          |

---

## Summary of Findings

### 1. WEX Inc. (https://www.wexinc.com/)
- **Grade:** D
- **Missing Headers:**
  - Content-Security-Policy
  - X-Frame-Options
  - X-Content-Type-Options
  - Referrer-Policy
  - Permissions-Policy
- **Implemented:**
  - Strict-Transport-Security (partial implementation)

**Recommendations:**
- Add all missing headers with secure configurations.
- Enhance `Strict-Transport-Security` with `includeSubDomains; preload`.

---

### 2. Box (https://www.box.com/)
- **Grade:** A (capped due to CSP warning)
- **Missing Headers:**
  - Referrer-Policy
  - Permissions-Policy
- **Weakness:**
  - Content-Security-Policy includes `'unsafe-inline'`, which reduces XSS protection.

**Recommendations:**
- Remove `'unsafe-inline'` from CSP.
- Add the missing headers to achieve stronger privacy and browser feature control.

---

### 3. ChatGPT (https://chatgpt.com/)
- **Grade:** A
- **Missing Header:**
  - Permissions-Policy
- **Implemented:**
  - Robust Content-Security-Policy
  - X-Content-Type-Options
  - Strict-Transport-Security
  - X-Frame-Options (via CSP `frame-ancestors`)
  - Referrer-Policy

**Recommendations:**
- Add a `Permissions-Policy` header to restrict access to browser APIs.
- Continue monitoring and updating CSP to align with evolving best practices.

---

## Learning Outcomes

- Gained practical experience evaluating HTTP response headers.
- Understood how security headers mitigate XSS, clickjacking, sniffing, and other attacks.
- Learned to interpret tools and reports used in real-world web security assessments.
- Built a checklist for secure web application configuration.

---

## Tools Used

- SecurityHeaders.com
- Manual HTTP response inspection
- Mozilla Observatory (recommended for further testing)

---

## Next Steps

- Automate header audits into CI/CD pipelines.
- Educate development teams on the impact of proper header usage.
- Align security configurations with OWASP recommendations.

---

