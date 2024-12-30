# Government Portal XSS

![Tools Used](https://img.shields.io/badge/Tools-Burp%20Suite%2C%20Dalfox%2C%20XSStrike-blue)

## Overview 📖
A **Reflected Cross-Site Scripting (XSS)** vulnerability was identified in the search functionality of a public government portal. This vulnerability allowed attackers to inject malicious scripts into the search query parameter, which were reflected in the resulting webpage.

Exploitation of this vulnerability could compromise user sessions, enable phishing attacks, or result in the theft of sensitive data.

---

## Exploitation Details 🚨
- **Affected Parameter:** `search`
- **Vulnerability Type:** Reflected XSS
- **Impact:**  
  - 🕵️‍♂️ Session Hijacking  
  - 🎣 Phishing Attacks  
  - 📂 Data Theft  

**Example Payloads:**
1. `<script>alert(1)</script>`  
2. `<script>alert(document.cookie)</script>`  
3. `<script>document.location="http://malicious.com"</script>`

---

## Exploitation Steps 🧩
1. Navigate to the government portal's search page.
2. Enter a malicious payload into the `search` parameter.
   - Example: `<script>alert(1)</script>`
3. Observe the execution of the injected script in the browser.

---

## Tools Used 🛠️
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | Crafting and testing payloads        |
| Dalfox          | Automated scanning for XSS issues   |
| XSStrike        | Fuzzing parameters for XSS payloads |
| Wayback Machine | Analyzing historical versions of the portal |

---

## Recommendations 🛡️
1. **Input Validation:** Validate and sanitize all user inputs against a strict whitelist of acceptable values.
2. **Output Encoding:** Ensure proper encoding of user inputs before rendering them on the webpage.
3. **Content Security Policy (CSP):** Implement a robust CSP to prevent unauthorized script execution.
4. **Regular Security Audits:** Continuously test and monitor the application for vulnerabilities.

---

## Disclaimer ⚠️
This example is provided for demonstration and educational purposes only. All details have been sanitized to remove any sensitive or proprietary information. Unauthorized use of this information is strictly prohibited.

