# Unauthenticated Alertmanager Access

## Overview 📖

During a penetration test, an instance of Prometheus Alertmanager was identified as publicly accessible without requiring authentication. This misconfiguration could allow unauthorized individuals to view, modify, or delete alerts, which could disrupt operations or lead to a denial-of-service condition.

---

## Details 🛠️

### Key Findings:
- **Vulnerability Location:**
  - Publicly accessible at `/#/alerts` endpoint.
- **Affected Application:**
  - Prometheus Alertmanager.
- **Issue Description:**
  - The Alertmanager web interface was accessible without any authentication controls.
  - Users could interact with alerts, potentially suppressing or resolving them, which could mislead incident response teams.

### Risk Impact:
- **Confidentiality:** Medium – Alert data could reveal sensitive operational information.
- **Integrity:** High – Alerts could be modified or suppressed maliciously.
- **Availability:** High – Alerts could be deleted, leading to missed critical events.

---

## Recommendations 🛡️

1. **Implement Authentication:**
   - Enable authentication on the Alertmanager instance to ensure that only authorized users can access it.
   - Use role-based access control (RBAC) to limit access based on user roles.

2. **Restrict Network Access:**
   - Limit access to the Alertmanager web interface by restricting its exposure to internal networks only.
   - Use firewalls or VPNs to control external access.

3. **Monitor and Audit:**
   - Regularly monitor access logs for unauthorized access attempts.
   - Conduct periodic audits to ensure authentication and access control policies are enforced.

4. **Update Documentation:**
   - Clearly document access control configurations in operational and security guidelines.

---

## Conclusion 🔒

By addressing the lack of authentication and restricting access to the Alertmanager instance, the organization can mitigate the risks of unauthorized access and ensure the integrity and availability of its alert management system. This proactive approach will enhance overall security posture and operational resilience.
