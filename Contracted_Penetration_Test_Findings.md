# Contracted Penetration Test Findings 🔍

This section highlights findings from targeted penetration tests conducted during contractual assessments. Each file contains detailed documentation of a specific vulnerability, the tools used, exploitation methodology, and recommendations for remediation.

---

## Findings Index
- [External Redirect Misconfiguration](#🌐-external-redirect-misconfiguration)
- [Web Server Denial of Service (DoS)](#💥-web-server-denial-of-service-dos)
- [Password Autocomplete Enabled](#🔒-password-autocomplete-enabled)
- [Session Signout Error](#🔁-session-signout-error)
- [ServiceNow Misconfigurations](#⚙️-servicenow-misconfigurations)


---

### 🌐 External Redirect Misconfiguration

#### Overview
An external redirect vulnerability was identified in a public-facing application during a contracted penetration test. This vulnerability allows attackers to redirect users to malicious websites by manipulating the `TransferUrl` parameter.

#### Example Vulnerable Request
```
https://verification.nws.noaa.gov/services/public/transfer.aspx?TransferUrl=https://malicious.site
```

#### Impact
- **Phishing**: Redirecting users to lookalike pages to steal credentials.
- **Malware Distribution**: Tricking users into downloading malicious files.
- **Brand Damage**: Users may associate the malicious activity with the legitimate domain.

#### Validation Steps
1. Access the vulnerable URL: `https://verification.nws.noaa.gov/services/public/transfer.aspx?TransferUrl=<attacker-controlled-url>`.
2. Observe redirection to the malicious domain.
3. Confirm no validation or sanitization of the `TransferUrl` parameter.

#### Recommendations
- Implement a whitelist for allowed redirect URLs.
- Reject or sanitize user-supplied values for the `TransferUrl` parameter.

---

### 💥 Web Server Denial of Service (DoS)

#### Overview
A Denial of Service (DoS) vulnerability was identified in a web server due to its inability to handle large or infinite HTTP header requests.

#### Example Vulnerable Request
```
GET / HTTP/1.1
Host: target.server
Referer: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX...
```

#### Impact
- **Server Resource Exhaustion**: The server may become unresponsive, affecting availability.
- **Service Downtime**: Legitimate users are unable to access resources.

#### Validation Steps
1. Send a crafted HTTP request with oversized headers to the target server.
2. Monitor the server’s response and resource usage.
3. Verify if the server becomes unresponsive or crashes.

#### Recommendations
- Configure a reverse proxy to filter out malformed or excessively large headers.
- Update the server software to the latest version to address known vulnerabilities.

---

### 🔒 Password Autocomplete Enabled

#### Overview
A web form contained password fields with the `autocomplete` attribute enabled, which may allow passwords to be saved in browsers and retrieved by unauthorized users.

#### Impact
- **Credential Exposure**: Sensitive credentials may be auto-filled on shared or compromised systems.

#### Validation Steps
1. Inspect the HTML source code of the login page.
2. Locate password fields and check for the presence of the `autocomplete` attribute.
3. Confirm if `autocomplete` is set to `on` or missing entirely.

#### Recommendations
- Add the `autocomplete="off"` attribute to all password fields in the web application.

---

### 🔁 Session Signout Error

#### Overview
During testing, a session signout error was observed, which could lead to user frustration or unauthorized access if sessions are not invalidated correctly.

#### Impact
- **User Confusion**: Users are unable to sign out properly.
- **Unauthorized Access**: Sessions may persist beyond their intended lifespan.

#### Validation Steps
1. Log into the application and initiate a session.
2. Attempt to sign out and monitor session termination behavior.
3. Verify if session cookies are cleared and invalidated server-side.

#### Recommendations
- Ensure that session cookies are cleared properly on logout.
- Validate session termination with server-side mechanisms.

---

### ⚙️ ServiceNow Misconfigurations

#### Overview
ServiceNow instances were observed to expose sensitive functionality or misconfigured options, potentially leading to unauthorized data access or manipulation.

#### Impact
- **Sensitive Data Exposure**: Attackers may gain access to internal data.
- **Unauthorized Changes**: Critical configurations could be altered.

#### Validation Steps
1. Access the exposed ServiceNow instance via its administrative URL.
2. Enumerate available modules and configurations.
3. Confirm unauthorized access to sensitive functionality or data.

#### Recommendations
- Restrict access to the ServiceNow administrative interface.
- Regularly audit ServiceNow configurations for adherence to security best practices.

---


