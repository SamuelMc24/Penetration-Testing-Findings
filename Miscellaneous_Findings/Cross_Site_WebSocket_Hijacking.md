# Cross-Site WebSocket Hijacking

![Risk Rating](https://img.shields.io/badge/Risk-High-red) ![Type](https://img.shields.io/badge/Type-Misconfiguration-blue)

## Overview 📖
WebSocket hijacking occurs when an application fails to validate the origin of WebSocket requests. This vulnerability allows attackers to establish unauthorized WebSocket connections on behalf of authenticated users, potentially leading to sensitive data exposure or manipulation of the application's state.

During testing, the WebSocket implementation of the application was found to lack proper origin validation, making it susceptible to cross-site hijacking attacks.

---

## Technical Details 🔍

### Description
The following misconfigurations were identified:
- **No Origin Validation:**
  - The application did not validate the `Origin` header in WebSocket requests, allowing connections from untrusted domains.
- **Session Reuse:**
  - The application reused user authentication tokens for WebSocket connections, enabling attackers to hijack sessions.

### Impact
The vulnerability could lead to:
1. **Sensitive Data Exposure:** Unauthorized access to real-time WebSocket communication.
2. **Session Hijacking:** Attackers can intercept and manipulate live user sessions.
3. **Application Abuse:** Exploitation of WebSocket functionality to perform unauthorized actions.

---

## Evidence 📂

### Example Vulnerable Request
**WebSocket Connection Request:**
```http
GET ws://target.server/ws/chat HTTP/1.1
Host: target.server
Origin: https://malicious.site

```
**Response:**
```http
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
```
- **Observation:** The server accepted the WebSocket connection without verifying the `Origin` header.

### Tools Used
- **Burp Suite:** Intercepted and analyzed WebSocket requests.
- **Browser DevTools:** Inspected WebSocket connection behavior.
- **Custom Payloads:** Simulated malicious cross-origin WebSocket requests.

---

## Recommendations 🛡️

1. **Validate Origin Header:**
   - Implement strict origin validation to ensure only trusted domains can establish WebSocket connections.

2. **Enforce Authentication Tokens:**
   - Require unique, session-specific tokens for WebSocket connections.

3. **Monitor WebSocket Activity:**
   - Log and analyze WebSocket traffic for anomalous patterns.

4. **Implement Rate Limiting:**
   - Restrict the number of WebSocket connections per user to prevent abuse.

5. **Regularly Audit Security Configurations:**
   - Perform periodic reviews of WebSocket configurations and implement updates as needed.

---

## Tools Used 🔧
| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| Burp Suite      | WebSocket testing and analysis       |
| Browser DevTools| Debugging and validation             |
| Custom Payloads | Simulating cross-origin attacks      |

---

## Disclaimer ⚠️
This page contains sanitized findings from real-world testing engagements. All sensitive details have been redacted to maintain confidentiality and comply with organizational policies. Unauthorized use of this information is strictly prohibited.
