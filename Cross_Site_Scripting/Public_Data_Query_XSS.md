# Public Data Query XSS

![Tools Used](https://img.shields.io/badge/Tools-Burp%20Suite%2C%20Dalfox%2C%20XSStrike-blue)

## Overview 📖
A **Reflected Cross-Site Scripting (XSS)** vulnerability was identified in a public data application's query string parameters. This vulnerability allowed attackers to inject malicious scripts via URL parameters, enabling actions such as credential theft and redirection to malicious websites.

---

## Exploitation Details 🚨
- **Affected Parameter:** `query`
- **Vulnerability Type:** Reflected XSS
- **Impact:**
  - 🔒 Credential Theft
  - 🌐 Redirection to Malicious Websites

**Example Payloads:**
1. `<script>alert(document.cookie)</script>`
2. `javascript:alert(1)`
3. `<script\x20type="text/javascript">javascript:alert(1);</script>`

---

## Exploitation Steps 🧩
1. Navigate to the public data application's URL with a vulnerable `query` parameter.
2. Inject a crafted payload into the query string.
   - Example: `https://example.com/data?query=<script>alert(document.cookie)</script>`
3. Observe the script execution or redirection occurring due to the reflected payload.

---

## Tools Used 🛠️
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | Crafting and testing payloads        |
| Dalfox          | Automated scanning for XSS issues   |
| XSStrike        | Fuzzing parameters for XSS payloads |
| Browser DevTools| Live debugging and validation        |

---

## Recommendations 🛡️
1. **Input Validation:** Sanitize all user inputs to prevent injection of malicious scripts.
2. **Output Encoding:** Properly encode reflected data before rendering it in the browser.
3. **Content Security Policy (CSP):** Implement a CSP to mitigate unauthorized script execution.
4. **URL Validation:** Strictly validate and encode all URL parameters.

---

## Disclaimer ⚠️
This example has been sanitized and is intended solely for educational purposes. It excludes any proprietary or sensitive details. Unauthorized use of this information is prohibited.
