# FTP Misconfigurations

![Tools Used](https://img.shields.io/badge/Tools-NMAP%2C%20Nuclei%2C%20FTP%20Client-blue)

## Overview 📖
FTP misconfigurations pose a significant risk to systems by enabling unauthorized access to sensitive data. Common issues include anonymous login, improper access controls, and the lack of encryption. These weaknesses can be exploited for data exfiltration, network reconnaissance, and launching further attacks.

This page consolidates findings related to FTP misconfigurations, highlighting sanitized examples from real-world penetration tests.

---

## Case Study: Anonymous FTP Login Enabled

**Risk Rating:** Medium (CVSS 5.7)  
**Type:** External Unauthenticated  
**Status:** Open  

### Description
A publicly accessible FTP server was found with anonymous login enabled. This allowed unauthenticated users to access files and directories without restriction, exposing internal system details and sensitive information.

### Impact
Potential exploitation scenarios include:
- Unauthorized data exfiltration.
- Internal network reconnaissance.
- Exploitation of exposed information for further attacks.

---

## Evidence 📂

### 1. Open FTP Port Detected
Nmap detected port 21 open, indicating an active FTP service.

**Command Used:**
```bash
nmap -p 21 -sV target.server
```

### 2. Anonymous Login
The FTP service permitted anonymous login, granting access to the file system.

**Commands Used:**
```bash
ftp target.server
Name: anonymous
Password: (none required)
```

### 3. File Enumeration and Download
The following actions were performed:
- Browsed directories.
- Downloaded publicly accessible files.

**Commands Used:**
```bash
ls
get <file>
```

---

## Recommendations 💡

1. **Disable Anonymous Login:** Prevent unauthorized access by requiring authentication for all users.
2. **Enable Encryption:** Use secure protocols such as FTPS or SFTP.
3. **Restrict Access:** Apply strict access controls and role-based permissions.
4. **Monitor FTP Activity:** Regularly review logs for unauthorized access attempts.
5. **Update FTP Software:** Ensure the server is running the latest version to mitigate known vulnerabilities.

---

## Tools Used 🛠️
| Tool         | Purpose                              |
|--------------|--------------------------------------|
| Nmap         | Port and service enumeration        |
| FTP Client   | Access and interaction with server  |
| Nuclei       | Vulnerability scanning and reporting|

---

## Disclaimer ⚠️
All findings presented here have been sanitized to remove sensitive details. This information is intended for educational purposes only and should not be used for unauthorized activities.
