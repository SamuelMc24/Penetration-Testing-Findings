# Cross-Site Scripting (XSS)

![Vulnerability: XSS](https://img.shields.io/badge/vulnerability-XSS-critical-red)  
![Tools: Burp Suite, OWASP ZAP](https://img.shields.io/badge/tools-Burp%20Suite%2C%20OWASP%20ZAP-blue)


## Overview 📖
Cross-Site Scripting (XSS) is a web vulnerability that allows attackers to inject malicious scripts into webpages viewed by other users. These scripts can execute in the browser context, enabling attackers to steal sensitive information, hijack sessions, or redirect users to malicious sites.

XSS vulnerabilities often arise due to insufficient input validation or improper output encoding. While these issues are common, their impact can range from low to critical depending on the nature of the vulnerable application and the data it handles.

---

## Categories of Findings 📂
This repository contains sanitized examples of XSS vulnerabilities I identified and exploited during real-world penetration tests. Each finding highlights the general methodology and tools used without disclosing sensitive details or proprietary information. Examples include:

1. [Site Hit Counter XSS](./Site_Hit_Counter_XSS.md)  
   - **Description:** Reflected XSS in a query parameter used for rendering site statistics.
   - **Impact:** Potential for session hijacking and unauthorized actions.

2. [Government Portal Search XSS](./Government_Portal_Search_XSS.md)  
   - **Description:** XSS in the search parameter of a public government portal.
   - **Impact:** Exfiltration of cookies and user credentials.

3. [Manual Search XSS](./Manual_Search_XSS.md)  
   - **Description:** Reflected XSS exploiting a search parameter in an online manual.
   - **Impact:** Malicious script execution in user browsers.

4. [Public Data Query XSS](./Public_Data_Query_XSS.md)  
   - **Description:** Reflected XSS exploiting URL query strings in a public data application.
   - **Impact:** Redirection to malicious websites and credential theft.

---

## Tools Used 🛠️
| Tool            | Purpose                        |
|-----------------|--------------------------------|
| Burp Suite      | Web application testing       |
| OWASP ZAP       | Web application security      |
| Nuclei          | Vulnerability automation      |
| Custom Payloads | Crafting and testing exploits |
| Browser DevTools| Script debugging and validation|

---

## Disclaimer ⚠️
This repository is for demonstration and educational purposes only. All findings have been sanitized to remove any sensitive or identifying information. The examples provided are intended to showcase penetration testing methodologies and best practices for identifying and remediating XSS vulnerabilities. Any unauthorized use of this information is strictly prohibited.
