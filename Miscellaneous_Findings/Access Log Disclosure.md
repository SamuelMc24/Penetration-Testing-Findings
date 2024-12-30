# Access Log Disclosure

![Risk Rating](https://img.shields.io/badge/Risk-Medium-yellow) ![Type](https://img.shields.io/badge/Type-Information_Disclosure-blue)

## Overview 📖
Access log files are critical for monitoring and troubleshooting application and server activity. However, when exposed to unauthorized users, these logs can provide attackers with valuable insights into the application’s behavior, internal IP addresses, session tokens, and other sensitive data.

This finding demonstrates the risks associated with publicly accessible access logs and provides recommendations to mitigate such exposures.

---

## Technical Details 🔍

### Description
During testing, publicly accessible access logs were identified at:
- **Endpoint:** `/logs/access.log`

These logs contained detailed HTTP request and response data, including:
- Client IP addresses
- User-Agent strings
- Timestamps
- Requested URIs
- HTTP status codes
- Referrer URLs

### Impact
The exposed logs could allow attackers to:
1. Enumerate valid endpoints and sensitive paths.
2. Identify internal IP addresses and network architecture.
3. Craft targeted attacks using session information or referrer data.
4. Perform reconnaissance for further exploitation.

---

## Evidence 📂

### Example Log Entry
```
127.0.0.1 - - [10/Dec/2024:14:32:01 +0000] "GET /admin HTTP/1.1" 403 1234 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"
```
- **Client IP:** `127.0.0.1`
- **URI:** `/admin`
- **Status Code:** `403`

### Tools Used
- **Nmap:** Enumerated open directories.
- **Burp Suite:** Validated the accessibility of the log file and analyzed its content.
- **Browser Inspection:** Confirmed access via direct browsing.

---

## Recommendations 🛡️

1. **Restrict Access:**
   - Configure web server rules to deny public access to log files (e.g., `.htaccess`, `nginx.conf`).

2. **Move Logs:**
   - Store log files outside of publicly accessible directories.

3. **Monitor Access:**
   - Implement logging for unauthorized access attempts to restricted files.

4. **Regular Audits:**
   - Conduct periodic reviews of web directories for unintended exposures.

5. **Enable Encryption:**
   - Use HTTPS to prevent attackers from intercepting sensitive log data during transmission.

---

## Tools Used 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Nmap            | Directory enumeration               |
| Burp Suite      | Manual testing and log analysis      |
| Browser DevTools| Direct file access validation        |

---

## Disclaimer ⚠️
All information provided here is sanitized and generalized for educational purposes. Unauthorized use of this data is strictly prohibited.
