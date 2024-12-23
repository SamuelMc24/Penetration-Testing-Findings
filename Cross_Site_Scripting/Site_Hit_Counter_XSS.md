# Site Hit Counter XSS

## Overview
This finding relates to a **Reflected Cross-Site Scripting (XSS)** vulnerability identified in the query parameters of a website's hit counter functionality. The vulnerability occurs because user-supplied input is improperly sanitized before being reflected in the webpage.

---

## Technical Details
- **Vulnerability Type:** Reflected XSS
- **Impact:** 
  - Session Hijacking
  - Unauthorized actions in a user's context
  - Potential for phishing attacks
- **Affected Parameter:** `count`
- **Payload Example:**
  ```html
  <script>alert('XSS')</script>
  ```

---

## Exploitation Steps
1. Navigate to the hit counter page with a vulnerable parameter.
2. Inject a payload into the `count` parameter.
3. Observe the execution of the malicious script in the browser.

---

## Tools Used
- **Burp Suite:** Crafting and testing payloads.
- **Wayback Machine:** Identifying older, vulnerable versions of the page.
- **Dalfox:** Scanning for XSS vulnerabilities.
- **XSStrike:** Automating payload generation.

---

## Recommendations
1. **Input Validation:** Ensure all input is properly sanitized and validated.
2. **Output Encoding:** Encode user-supplied data before rendering it in the browser.
3. **Content Security Policy (CSP):** Implement a strict CSP to mitigate XSS attacks.

---

## Disclaimer
This example has been sanitized and is for educational purposes only. It does not contain any sensitive or identifying details about the specific application.
