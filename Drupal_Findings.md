# Drupal Findings

![Tools Used](https://img.shields.io/badge/Tools-Burp%20Suite%2C%20Nuclei%2C%20Custom%20Scripts-blue)

## Overview 📖
Drupal is a widely used Content Management System (CMS) responsible for managing permissions, roles, and website content. Misconfigurations or exposed endpoints in Drupal can lead to user enumeration, exposing sensitive user identities and increasing the risk of attacks like brute force or credential stuffing. 

This section consolidates findings from multiple engagements where Drupal misconfigurations led to potential information disclosure.

---

## Key Findings 🚨

### 1. Exposed User Enumeration Endpoint
- **Affected Endpoint:** `/jsonapi/user/user`
- **Risk Rating:** Medium (CVSS 6.8)
- **Description:** Publicly accessible JSON endpoints allowed attackers to enumerate usernames associated with the application.
- **Impact:**
  - Enabled brute force and credential stuffing attacks.
  - Increased risk of privilege escalation or unauthorized access to sensitive information.
- **Recommendations:**
  1. Restrict access to sensitive JSON endpoints using authentication and role-based controls.
  2. Disable unnecessary API endpoints to minimize exposure.
  3. Obfuscate or replace identifiable user information with anonymous placeholders.

### 2. Exposed Login Pages
- **Description:** Publicly accessible Drupal login pages provided verbose error messages when incorrect credentials were used, allowing attackers to confirm valid usernames.
- **Impact:**
  - Assisted in verifying existing accounts for targeted attacks.
  - Enabled enumeration of valid usernames.
- **Recommendations:**
  1. Restrict access to login pages via IP whitelisting.
  2. Implement generic error messages for failed login attempts.
  3. Enforce Multi-Factor Authentication (MFA) to reduce brute force risks.

---

## Exploitation Risks 🛠️
1. **Credential Stuffing Attacks:** Attackers can use leaked credentials from other breaches to access accounts.
2. **Brute Force Attacks:** Systematic password guessing using enumerated usernames.
3. **Privilege Escalation:** Using valid usernames to gain unauthorized administrative access.

---

## Tools and Methodologies 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | Testing API endpoints and login pages |
| Nuclei          | Automated detection of exposed endpoints |
| Custom Scripts  | Automated enumeration and validation |

---

## Recommendations 🛡️
1. **Restrict Access to Admin Panels:** Use IP whitelisting and authentication to limit access.
2. **Disable Unnecessary Endpoints:** Remove or restrict `/jsonapi/user/user` and other sensitive endpoints.
3. **Sanitize Error Messages:** Avoid exposing sensitive information in error responses.
4. **Periodic Security Audits:** Regularly review and harden Drupal configurations.

---

## Disclaimer ⚠️
This page contains sanitized findings from real-world testing engagements. All sensitive details have been redacted to maintain confidentiality and compliance with organizational policies.
