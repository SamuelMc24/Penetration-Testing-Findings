# Git Misconfigurations

## Overview 📖
Git misconfigurations can expose sensitive application configuration files or even the entire source code repository, leading to unauthorized access, data breaches, and other security risks. Common misconfigurations include leaving `.git` directories publicly accessible or exposing the `.git/config` file, which may reveal sensitive information about the application, its dependencies, or credentials.

As a Penetration Tester, I have identified multiple instances of Git misconfigurations, resulting in high-severity findings reported to government agencies. Below are sanitized examples demonstrating my methodologies, tools used, and recommendations provided.

---

## Findings 📂

### Finding 1: Exposed `.git/config` File
- **Description:** The application exposed the `.git/config` file, which contained sensitive metadata about the repository. This could potentially allow an attacker to clone the repository or gather information to exploit other vulnerabilities.
- **Impact:** Unauthorized access to source code, leading to the discovery of other vulnerabilities or sensitive information.
- **Recommendation:**
  1. Restrict access to the `.git` directory using web server configurations.
  2. Relocate `.git` directories outside the web root.
  3. Implement firewall rules to block access to sensitive paths.
  4. Regularly scan and validate exposed directories for misconfigurations.
- **References:** CWE-200: Information Exposure

---

### Finding 2: Directory Browsing Enabled for `.git`
- **Description:** Directory browsing was enabled for the `.git` directory, allowing unauthorized users to view its contents and download the repository.
- **Impact:** Unauthorized access to source code, configuration files, and sensitive data.
- **Recommendation:**
  1. Disable directory browsing in the web server configuration.
  2. Set proper permissions to restrict access to sensitive directories.
  3. Regularly review and harden web server configurations.
- **References:** CWE-548: Exposure of Information Through Directory Listing

---

### Tools and Methodologies 🛠️
| Tool            | Purpose                        |
|-----------------|--------------------------------|
| Burp Suite      | Web application testing       |
| Nmap            | Network scanning and enumeration |
| Nikto           | Web server scanning           |
| Custom Scripts  | Directory and file enumeration |
| Wayback Machine | Historical content analysis   |

---

## Key Recommendations 🌟
1. **Secure Web Server Configurations:**
   - Disable directory browsing.
   - Restrict access to sensitive paths using `.htaccess` or equivalent configurations.
2. **Relocate Sensitive Directories:**
   - Move `.git` directories outside of the web root to prevent accidental exposure.
3. **Continuous Monitoring:**
   - Automate scans to identify exposed directories and configuration files.
4. **Employee Training:**
   - Educate developers and administrators on secure development and deployment practices.

---

## Disclaimer ⚠️
This page is for demonstration purposes only and contains sanitized examples of vulnerabilities identified during professional engagements. All sensitive details have been redacted to maintain confidentiality and compliance with organizational policies.
