# WordPress User Enumeration

![Tools Used](https://img.shields.io/badge/Tools-Burp%20Suite%2C%20OWASP%20ZAP%2C%20Nuclei-blue)

## Overview 📖
WordPress user enumeration vulnerabilities enable attackers to identify valid usernames by exploiting publicly accessible endpoints or verbose login responses. These weaknesses can be leveraged for brute-force attacks or other unauthorized activities. Across several government systems, I identified and reported user enumeration vulnerabilities, showcasing the critical need for access controls and response hardening.

---

## Key Findings 🚨

### 1. Exposed API Endpoints
- **Affected Endpoints:** `/wp-json/wp/v2/users` or `/?author=<ID>`
- **Observation:** These endpoints revealed a complete list of usernames without requiring authentication.
- **Impact:** Provided attackers with direct insight into valid usernames, enabling targeted password-guessing attacks.
- **Mitigation:** Restrict public access to these endpoints using access control rules or plugins.

### 2. Verbose Login Responses
- **Affected Pages:** Login and password reset pages.
- **Observation:** Differentiated responses for valid and invalid usernames disclosed account existence.
- **Impact:** Allowed attackers to verify accounts for targeted attacks or phishing attempts.
- **Mitigation:** Provide a generic response to both valid and invalid inputs.

### 3. Enumeration via Browser Extensions
- **Scenario:** Some sites inadvertently exposed usernames through HTML meta tags or plugins that displayed author profiles.
- **Observation:** Usernames were discoverable without accessing the admin panel.
- **Impact:** Increased the attack surface for brute-force and phishing attacks.
- **Mitigation:** Review and sanitize metadata and disable unnecessary plugin features.

---

## Exploitation Risks 🛠️
1. **Credential Stuffing Attacks:** Using identified usernames in combination with leaked passwords from data breaches.
2. **Brute-Force Login Attempts:** Systematic guessing of passwords using known usernames.
3. **Phishing Campaigns:** Crafting targeted phishing emails using exposed account information.

---

## Recommendations 🛡️
1. **Restrict Endpoint Access:** Use access controls to limit API exposure to authenticated users only.
2. **Sanitize Login Responses:** Provide uniform responses for login failures.
3. **Deploy Security Plugins:** Use WordPress security plugins to obfuscate or disable sensitive endpoints.
4. **Enforce MFA:** Implement Multi-Factor Authentication (MFA) for enhanced login security.
5. **Conduct Regular Audits:** Periodically review exposed endpoints and plugins for potential leaks.

---

## Tools Used 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | Manual payload crafting and testing |
| OWASP ZAP       | Automated vulnerability scanning    |
| Nuclei          | Endpoint vulnerability detection    |
| cURL            | Manual API enumeration and testing  |

---

## Summary of Expertise 🌟
Through comprehensive analysis of WordPress sites, I identified and mitigated vulnerabilities affecting various systems. My findings included exposed API endpoints, verbose login responses, and metadata leaks. By leveraging tools like Burp Suite, Nuclei, and OWASP ZAP, I delivered actionable insights and practical solutions to improve security posture.

---

## Disclaimer ⚠️
All examples are sanitized and are intended for educational purposes only. Unauthorized use of this information is strictly prohibited.
