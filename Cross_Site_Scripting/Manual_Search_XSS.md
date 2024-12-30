# Manual Search XSS

![Tools Used](https://img.shields.io/badge/Tools-Burp%20Suite%2C%20Dalfox%2C%20XSStrike-blue)

## Overview 📖
A **Reflected Cross-Site Scripting (XSS)** vulnerability was discovered in the manual search functionality of a government documentation platform. This issue allowed attackers to inject malicious scripts into search parameters, enabling them to manipulate webpage behavior and extract sensitive information.

---

## Exploitation Details 🚨
- **Affected Parameter:** `query`
- **Vulnerability Type:** Reflected XSS
- **Impact:**
  - 🕵️‍♂️ Session Hijacking
  - 📋 Exfiltration of Cookies
  - 📂 Redirection to Malicious Websites

**Example Payloads:**
1. `<script>alert(1)</script>`
2. `');alert(1);//`
3. `" onmouseover="alert(1)`
4. `javascript:alert(1)`

---

## Exploitation Steps 🧩
1. Access the manual search page on the affected platform.
2. Insert a crafted payload into the `query` parameter.
   - Example: `<script>alert(1)</script>`
3. Observe the execution of the malicious script when the search results are rendered.

---

## Tools Used 🛠️
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | Payload crafting and testing         |
| Dalfox          | XSS scanning and payload injection   |
| XSStrike        | Automated payload generation         |
| Browser DevTools| Live debugging and verification      |

---

## Recommendations 🛡️
1. **Input Validation:** Implement strict whitelisting for user inputs to prevent injection of unauthorized scripts.
2. **Output Encoding:** Sanitize all dynamic content rendered in the browser.
3. **Content Security Policy (CSP):** Deploy a robust CSP to mitigate script execution risks.
4. **Regular Security Testing:** Conduct frequent assessments to identify and remediate vulnerabilities proactively.

---

## Disclaimer ⚠️
This example has been sanitized and is intended solely for educational purposes. It excludes any proprietary or sensitive details. Unauthorized use of this information is prohibited.
