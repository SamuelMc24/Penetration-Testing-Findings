# Cross-Site Scripting (XSS)

## Overview
Cross-Site Scripting (XSS) is a web vulnerability that allows attackers to inject malicious scripts into webpages viewed by other users. These scripts can execute in the browser context, enabling attackers to steal sensitive information, hijack sessions, or redirect users to malicious sites. 

XSS vulnerabilities often arise due to insufficient input validation or improper output encoding. While these issues are common, their impact can range from low to critical depending on the nature of the vulnerable application and the data it handles.

## Categories of Findings
This repository contains sanitized examples of XSS vulnerabilities I identified and exploited during real-world penetration tests. Each finding highlights the general methodology and tools used without disclosing sensitive details or proprietary information. Examples include:

1. [Site Hit Counter XSS](./Site_Hit_Counter_XSS.md)  
   Description: Reflected XSS in a query parameter used for rendering site statistics.
2. [Portal Search XSS](./Government_Portal_Search_XSS.md)  
   Description: XSS in the search parameter of a public government portal.
3. [Manual Search XSS](./Manual_Search_XSS.md)  
   Description: Reflected XSS exploiting a search parameter in an online manual.
4. [Public Data Query XSS](./Public_Data_Query_XSS.md)  
   Description: Reflected XSS exploiting URL query strings in a public data application.

## Tools Used
A variety of tools and methodologies were employed to identify and validate these findings, including:
- Burp Suite
- OWASP ZAP
- Custom payload generation
- Nuclei
- Browser developer tools

## Disclaimer
This repository is for demonstration and educational purposes only. All findings have been sanitized to remove any sensitive or identifying information. The examples provided are intended to showcase penetration testing methodologies and best practices for identifying and remediating XSS vulnerabilities. Any unauthorized use of this information is strictly prohibited.

