# SharePoint Misconfiguration

![Risk Rating](https://img.shields.io/badge/Risk-High-red) ![Type](https://img.shields.io/badge/Type-Misconfiguration-blue)

## Overview 📖
SharePoint is a widely used collaboration platform for managing content and documents. Misconfigurations, such as exposing sensitive files or granting excessive permissions, can lead to unauthorized access to confidential information. During testing, several SharePoint environments were identified with misconfigurations that exposed sensitive data and internal documentation.

---

## Technical Details 🔍

### Description
The following SharePoint misconfigurations were identified:
- **Publicly Accessible Files:** Documents and folders containing sensitive information were accessible without authentication.
- **Improper Permissions:** Excessive permissions were granted to anonymous or guest users.
- **Exposed Administrative Pages:** Configuration and administrative interfaces were accessible, increasing the risk of unauthorized changes.

### Impact
These misconfigurations increase the risk of:
1. Unauthorized access to sensitive corporate or government data.
2. Information disclosure that could aid attackers in crafting targeted attacks.
3. Potential compromise of internal systems due to exposed administrative access.

---

## Evidence 📂

### Example Exposed File
The following file was discovered during enumeration:
```
/sharepoint/documents/internal_policy.docx
```
- Contained sensitive information about internal workflows and procedures.

### Tools Used
- **Nmap:** Enumerated accessible directories and services.
- **Burp Suite:** Validated exposure and analyzed responses.
- **Browser Inspection:** Verified access to SharePoint sites and files.

---

## Recommendations 🛡️

1. **Restrict Public Access:**
   - Configure SharePoint permissions to limit access to authenticated users only.

2. **Audit Permissions:**
   - Regularly review and adjust permissions to follow the principle of least privilege.

3. **Secure Administrative Pages:**
   - Restrict access to configuration and administrative interfaces using IP whitelisting or VPN access.

4. **Enable Logging and Monitoring:**
   - Track access attempts and review logs for unauthorized activities.

5. **Conduct Security Assessments:**
   - Periodically test SharePoint environments for misconfigurations and vulnerabilities.

---

## Tools Used 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | Manual validation and payload testing |
| Nmap            | Directory and service enumeration    |
| Browser DevTools| Debugging and access validation       |

---

## Disclaimer ⚠️
This page contains sanitized findings from real-world testing engagements. All sensitive details have been redacted to maintain confidentiality and comply with organizational policies. Unauthorized use of this information is strictly prohibited.
