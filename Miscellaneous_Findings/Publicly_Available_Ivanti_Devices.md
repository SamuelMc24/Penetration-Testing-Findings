# Publicly Available Ivanti Devices

![Risk Rating](https://img.shields.io/badge/Risk-Critical-red) ![Type](https://img.shields.io/badge/Type-Misconfiguration-blue)

## Overview 📖
Ivanti devices, including VPN and endpoint management solutions, are critical components of enterprise infrastructure. Misconfigurations that expose these devices to the internet without authentication create severe risks, including unauthorized access, data breaches, and potential remote code execution (RCE).

During testing, multiple Ivanti VPN endpoints were found publicly accessible without authentication mechanisms in place.

---

## Technical Details 🔍

### Description
The following observations were made:
- Exposed Ivanti VPN endpoints responding to HTTP/HTTPS requests.
- Lack of proper authentication requirements, allowing unauthenticated users access to administrative interfaces.
- Potential exposure of session management and sensitive configuration data.

### Impact
The exposed Ivanti devices could lead to:
1. **Unauthorized Access:** Attackers can manipulate configurations or gain unauthorized VPN access.
2. **Sensitive Data Exposure:** Potential leak of user credentials, session tokens, or configuration settings.
3. **Remote Exploitation:** If the devices are running vulnerable firmware, attackers may exploit known CVEs (e.g., CVE-2023-35078).

---

## Evidence 📂

### Identified Endpoints
- Ivanti VPN was found accessible at the following endpoint:
  ```
  https://target.server
  ```

### Tools Used
- **Nmap:** Identified open ports and verified HTTP/HTTPS services.
- **Browser Inspection:** Verified exposed login pages and interface availability.
- **Vulnerability Scanning:** Confirmed firmware version and CVE applicability.

---

## Recommendations 🛡️

1. **Restrict Public Access:**
   - Use firewall rules to block unauthorized IP addresses from accessing Ivanti devices.

2. **Enable Authentication:**
   - Ensure that all administrative interfaces require multi-factor authentication (MFA).

3. **Apply Patches:**
   - Immediately update to the latest Ivanti firmware to address any known vulnerabilities.

4. **Monitor Device Activity:**
   - Implement logging and monitoring to detect unauthorized access attempts.

5. **Segment Networks:**
   - Place Ivanti devices behind a secure VPN or private network to limit exposure.

---

## Tools Used 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Nmap            | Service and port enumeration        |
| Burp Suite      | Manual validation and interface testing |
| Nessus          | Vulnerability scanning              |

---

## Disclaimer ⚠️
This page contains sanitized findings from real-world testing engagements. All sensitive details have been redacted to maintain confidentiality and comply with organizational policies. Unauthorized use of this information is 
