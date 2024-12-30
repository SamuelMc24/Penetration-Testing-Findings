# Miscellaneous Findings

![Tools Used](https://img.shields.io/badge/Tools-Burp%20Suite%2C%20OWASP%20ZAP%2C%20Nuclei-blue)

## Overview 📖
This section showcases a diverse range of unique findings identified during penetration testing engagements. These findings highlight vulnerabilities that do not fit into standard categories yet demonstrate critical risks to systems, including exposed administrative interfaces, configuration leaks, and misconfigurations in web services and protocols. By addressing these vulnerabilities, organizations can significantly reduce their attack surface.

---

## Table of Findings 📂

1. [Access Log Disclosure](./Access_Log_Disclosure.md)
   - **Description:** Sensitive server logs exposed publicly, revealing detailed request and response data.
   - **Impact:** Provides attackers with valuable insights into application behavior and potential vulnerabilities.

2. [Django Stack Error](./Django_Stack_Error.md)
   - **Description:** Detailed debug information revealed through misconfigured error handling in Django applications.
   - **Impact:** Enables attackers to identify framework versions and potential weaknesses.

3. [Exposed MSSQL Server](./Exposed_MSSQL_Server.md)
   - **Description:** Publicly accessible Microsoft SQL Server allowing unauthenticated connections.
   - **Impact:** Allows attackers to access or manipulate sensitive data stored in the database.

4. [Publicly Available Ivanti Devices](./Publicly_Available_Ivanti_Devices.md)
   - **Description:** Misconfigured Ivanti VPN endpoints exposed to the internet without authentication.
   - **Impact:** Increases risk of unauthorized access to sensitive network resources.

5. [SharePoint Misconfiguration](./SharePoint_Misconfiguration.md)
   - **Description:** Misconfigured SharePoint environments exposing sensitive files and directories.
   - **Impact:** Enables unauthorized access to confidential documents and internal communication.

6. [ColdFusion Admin Page Exposure](./ColdFusion_Admin_Page_Exposure.md)
   - **Description:** Exposed administrative interfaces for ColdFusion servers without proper access controls.
   - **Impact:** Allows attackers to control server settings and potentially execute malicious actions.

7. [CORS Arbitrary Origin Trusted](./CORS_Arbitrary_Origin_Trusted.md)
   - **Description:** Misconfigured CORS policies allowing access from arbitrary origins.
   - **Impact:** Exposes sensitive data to unauthorized third-party domains.

8. [Cross-Site WebSocket Hijacking](./Cross_Site_WebSocket_Hijacking.md)
   - **Description:** Lack of origin validation in WebSocket connections.
   - **Impact:** Enables attackers to hijack WebSocket sessions and intercept sensitive data.

9. [Unauthenticated Alertmanager Access](./Unauthenticated_Alertmanager_Access.md)
   - **Description:** Publicly accessible monitoring dashboards without authentication.
   - **Impact:** Provides attackers with operational insights into system health and metrics.

10. [Exposed Keycloak Administrative Interface](./Exposed_Keycloak_Administrative_Interface.md)
    - **Description:** Keycloak admin interfaces exposed without authentication.
    - **Impact:** Allows attackers to manipulate authentication settings or access user data.

---

## Tools and Techniques 🔧
| Tool             | Purpose                               |
|------------------|---------------------------------------|
| Burp Suite       | Manual testing and vulnerability discovery |
| OWASP ZAP        | Automated scanning for web vulnerabilities |
| Nuclei           | Pattern-based vulnerability scanning  |
| Custom Scripts   | Tailored testing for specific environments |
| Wayback Machine  | Historical content analysis          |

---

## Disclaimer ⚠️
This repository contains sanitized findings from real-world penetration tests. Sensitive details have been redacted to maintain confidentiality and comply with organizational policies. All examples are for demonstration and educational purposes only.
