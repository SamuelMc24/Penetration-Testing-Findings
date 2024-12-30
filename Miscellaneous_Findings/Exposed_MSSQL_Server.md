# Exposed MSSQL Server

![Risk Rating](https://img.shields.io/badge/Risk-High-red) ![Type](https://img.shields.io/badge/Type-Misconfiguration-blue)

## Overview 📖
An exposed Microsoft SQL Server (MSSQL) occurs when the server is accessible over the internet without proper authentication or access controls. This misconfiguration can lead to unauthorized access, data theft, and further compromise of the associated systems.

During testing, an MSSQL server was found accessible over the internet without requiring authentication, exposing it to potential exploitation.

---

## Technical Details 🔍

### Description
The MSSQL server was discovered during an enumeration phase and was found to:
- Respond to connection attempts without authentication.
- Expose sensitive database information, including table names and schemas.

### Impact
The exposed MSSQL server increases the risk of:
1. Unauthorized data access and potential theft of sensitive information.
2. Exploitation via known vulnerabilities in outdated MSSQL versions.
3. Lateral movement within the network if the server is part of a larger infrastructure.

---

## Evidence 📂

### Commands Used

#### Nmap Scan
Identified the exposed MSSQL service:
```bash
nmap -p 1433 --script ms-sql-info target.server
```

#### SQL Command Line Interaction
Connected to the server without requiring credentials:
```sql
sqlcmd -S target.server -U sa -P ""
```
- **Result:** Access granted with administrative privileges.

---

## Recommendations 🛡️

1. **Restrict Public Access:**
   - Configure firewalls to block external access to port 1433 (MSSQL default port).

2. **Enforce Authentication:**
   - Ensure all accounts require strong, unique passwords.

3. **Disable SA Account:**
   - Disable the default `sa` account if not required, and use role-based accounts with least privileges.

4. **Enable Encryption:**
   - Use TLS to secure MSSQL communications and prevent data interception.

5. **Regularly Patch and Update:**
   - Ensure the MSSQL server and associated software are updated to the latest versions.

6. **Monitor and Audit Logs:**
   - Regularly review server logs for unauthorized access attempts.

---

## Tools Used 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Nmap            | Service discovery and enumeration   |
| sqlcmd          | Interaction with MSSQL server       |
| Burp Suite      | Testing and validating configurations |

---

## Disclaimer ⚠️
This page contains sanitized findings from real-world testing engagements. All sensitive details have been redacted to maintain confidentiality and comply with organizational policies. Unauthorized use of this information is strictly prohibited.
