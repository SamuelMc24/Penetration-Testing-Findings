# Penetration Testing Findings

![Repository Overview](https://img.shields.io/badge/status-active-brightgreen) ![License](https://img.shields.io/badge/license-MIT-green) ![Technologies](https://img.shields.io/badge/tools-Burp%20Suite%2C%20Kali%20Linux%2C%20Dalfox%2C%20XSStrike-blue)

## Table of Contents
- [Overview 📖](#overview-📖)
- [Categories of Findings 📊](#categories-of-findings-📊)
- [Tools Used 🔧](#tools-used-🔧)
- [Purpose 🌐](#purpose-🌐)
- [Disclaimer ⚠️](#disclaimer-⚠️)

## Overview 📖
This repository highlights real-world vulnerabilities exploited during my time as a Penetration Tester at ECS Federal, where I contributed to securing government systems through both continuous monitoring and scheduled penetration testing. Working under a contract covering over 25,000 hosts across various government bureaus, I identified and exploited vulnerabilities in systems, networks, and web applications.

The repository includes examples of findings such as:

- **Cross-Site Scripting (XSS):** Exploiting input validation flaws to execute malicious scripts.
- **End-of-Life (EOL) Software:** Scanning and identifying outdated software versions, leading to critical severity reports.
- **Information Disclosures:** Discovering sensitive files and data exposed to the public, impacting confidentiality and compliance.

Each section showcases sanitized findings, the tools and methodologies used, and the results delivered to clients. In addition to penetration testing, I served as the SME for my team on Recorded Future, utilizing the tool to identify vulnerabilities, write documentation, and train team members.

## Categories of Findings 📊
- [Cross-Site Scripting (XSS)](./Cross_Site_Scripting)
- [End-of-Life (EOL) Software](./EOL_Software.md)
- [Information Disclosures](./Information_Disclosures.md)
- [FTP Misconfigurations](./FTP_Misconfigurations.md)
- [WordPress User Enumeration](./WordPress_User_Enumeration.md)
- [Git Misconfigurations](./Git_Misconfigurations)
- [Drupal Findings](./Drupal_Findings)
- [Miscellaneous Findings](./Miscellaneous_Findings)

## Tools Used 🔧
| Tool            | Purpose                        |
|-----------------|--------------------------------|
| Burp Suite      | Web application testing       |
| Kali Linux      | Penetration testing platform  |
| Dalfox          | XSS vulnerability scanning    |
| XSStrike        | Automated XSS payload testing |
| Nessus          | Vulnerability scanning        |
| OWASP ZAP       | Web application security      |
| Splunk          | Log and data analysis         |
| Nuclei          | Vulnerability automation      |
| Appscan         | Dynamic application security  |
| Recorded Future | Threat intelligence platform  |
| NMAP            | Network scanning              |
| Metasploit      | Exploitation framework        |
| Nikto           | Web server scanning           |
| sqlmap          | SQL injection testing         |
| wpscan          | WordPress vulnerability scans |

## Purpose 🌐
This repository is designed to demonstrate my hands-on experience with penetration testing and real-world exploitation of vulnerabilities. By showcasing a diverse range of findings, I aim to highlight my technical skills, problem-solving abilities, and adherence to professional testing methodologies.

## Disclaimer ⚠️
All examples provided in this repository are sanitized and generalized to remove any sensitive or identifying information. They are intended for demonstration purposes only and do not disclose any proprietary or government-related details.
