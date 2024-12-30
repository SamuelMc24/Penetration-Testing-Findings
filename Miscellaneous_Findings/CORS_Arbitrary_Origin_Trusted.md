# CORS Arbitrary Origin Trusted

![Risk Rating](https://img.shields.io/badge/Risk-High-red) ![Type](https://img.shields.io/badge/Type-Misconfiguration-blue)

## Overview 📖
Cross-Origin Resource Sharing (CORS) is a mechanism that allows controlled access to resources on a web server from a different origin. A misconfiguration that trusts arbitrary origins can expose sensitive data, enabling malicious actors to exploit vulnerabilities and perform unauthorized actions.

During testing, the application was found to accept arbitrary origins in its CORS configuration, significantly increasing the risk of data exfiltration.

---

## Technical Details 🔍

### Description
The following misconfigurations were identified:
- **CORS Policy Misconfiguration:**
  - The application returned a wildcard `*` in the `Access-Control-Allow-Origin` header, or dynamically echoed the `Origin` header without validation.
- **Sensitive Endpoints Affected:**
  - API endpoints containing sensitive user and system data were accessible from untrusted origins.

### Impact
The misconfigured CORS policy could lead to:
1. **Data Exfiltration:** Malicious websites can make authenticated requests to the vulnerable application on behalf of the user and access sensitive information.
2. **Credential Theft:** Unauthorized access to tokens, cookies, or session data.
3. **Privilege Escalation:** Exploitation of additional vulnerabilities using trusted user credentials.

---

## Evidence 📂

### Identified Vulnerable Response
**Request:**
```http
GET /api/v1/data HTTP/1.1
Host: target.server
Origin: https://malicious.site
```

**Response:**
```http
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://malicious.site
Access-Control-Allow-Credentials: true
```

### Tools Used
- **Burp Suite:** Validated the presence of CORS misconfiguration.
- **Browser DevTools:** Analyzed CORS headers and cross-origin requests.
- **Nuclei:** Automated detection of CORS misconfigurations.

---

## Recommendations 🛡️

1. **Restrict CORS Policies:**
   - Define a specific set of trusted origins in the `Access-Control-Allow-Origin` header.

2. **Avoid Dynamic Echoing:**
   - Avoid dynamically reflecting the `Origin` header without validation.

3. **Disable Credentials Sharing:**
   - Set `Access-Control-Allow-Credentials` to `false` unless explicitly required, and ensure it is limited to trusted origins.

4. **Regularly Audit Configurations:**
   - Periodically review CORS policies for security and compliance.

5. **Implement Logging and Monitoring:**
   - Track and analyze cross-origin requests for anomalies.

---

## Tools Used 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | Manual testing and header analysis  |
| Browser DevTools| Debugging and request validation     |
| Nuclei          | Automated CORS misconfiguration detection |

---

## Disclaimer ⚠️
This page contains sanitized findings from real-world testing engagements. All sensitive details have been redacted to maintain confidentiality and comply with organizational policies. Unauthorized use of this information is strictly prohibited.
