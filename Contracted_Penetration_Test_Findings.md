# Contracted Penetration Test Findings 🔍

This section highlights findings from targeted penetration tests conducted during contractual assessments. Each file contains detailed documentation of a specific vulnerability, the tools used, exploitation methodology, and recommendations for remediation.

---

## Findings Index
- [External Redirect Misconfiguration](#external-redirect-misconfiguration)
- [Web Server Denial of Service (DoS)](#web-server-denial-of-service-dos)
- [Password Autocomplete Enabled](#password-autocomplete-enabled)
- [Session Signout Error](#session-signout-error)
- [ServiceNow Misconfigurations](#servicenow-misconfigurations)

---

### External Redirect Misconfiguration

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

#### Evidence
![ZAP Alert](../images/external_redirect_ZAP.JPG)
![Successful Redirect](../images/successful_redirect_CNN.JPG)

#### Recommendations
- Implement a whitelist for allowed redirect URLs.
- Reject or sanitize user-supplied values for the `TransferUrl` parameter.

---

### Web Server Denial of Service (DoS)

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

#### Evidence
![Nessus DoS Alert](../images/Dos_vuln_SpectrumXXI.PNG)

#### Recommendations
- Configure a reverse proxy to filter out malformed or excessively large headers.
- Update the server software to the latest version to address known vulnerabilities.

---

### Password Autocomplete Enabled

#### Overview
A web form contained password fields with the `autocomplete` attribute enabled, which may allow passwords to be saved in browsers and retrieved by unauthorized users.

#### Impact
- **Credential Exposure**: Sensitive credentials may be auto-filled on shared or compromised systems.

#### Evidence
![Password Autocomplete Alert](../images/password_autocomplete_global_protect.PNG)

#### Recommendations
- Add the `autocomplete="off"` attribute to all password fields in the web application.

---

### Session Signout Error

#### Overview
During testing, a session signout error was observed, which could lead to user frustration or unauthorized access if sessions are not invalidated correctly.

#### Impact
- **User Confusion**: Users are unable to sign out properly.
- **Unauthorized Access**: Sessions may persist beyond their intended lifespan.

#### Evidence
![Session Signout Error](../images/sign_out_issue.JPG)

#### Recommendations
- Ensure that session cookies are cleared properly on logout.
- Validate session termination with server-side mechanisms.

---

### ServiceNow Misconfigurations

#### Overview
ServiceNow instances were observed to expose sensitive functionality or misconfigured options, potentially leading to unauthorized data access or manipulation.

#### Impact
- **Sensitive Data Exposure**: Attackers may gain access to internal data.
- **Unauthorized Changes**: Critical configurations could be altered.

#### Evidence
![ServiceNow Misconfiguration](../images/servicenow_Wapp.JPG)

#### Recommendations
- Restrict access to the ServiceNow administrative interface.
- Regularly audit ServiceNow configurations for adherence to security best practices.

---
