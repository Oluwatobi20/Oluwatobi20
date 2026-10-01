# R-01 Control Mapping & Evidence Matrix

| Risk ID | Risk Scenario | Control | Primary CSF Function | Evidence Requested | Test Objective | Assessment Status |
|---|---|---|---|---|---|---|
| R-01 | Credential phishing affecting payroll | MFA | PROTECT | IAM/authentication configuration | Verify MFA is enforced for in-scope payroll access | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | MFA | PROTECT | MFA enrolment report | Verify required population is enrolled and investigate exceptions | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | MFA | PROTECT | Authentication logs | Verify MFA operates during actual authentication attempts | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | MFA | PROTECT | Controlled access test | Confirm password-only access is denied | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Security awareness / phishing training | PROTECT | To be developed | To be developed | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Least privilege | PROTECT | Payroll access-control matrix / RBAC role definitions | Verify approved roles, permissions and business justification reflect least privilege | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Least privilege | PROTECT | Current payroll access export + AD / Entra ID group membership | Compare actual access against approved access and identify excessive, stale or unauthorised access | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Least privilege | PROTECT | Joiner/Mover/Leaver tickets + periodic access-review evidence | Verify access is provisioned, changed and revoked appropriately and periodically recertified by an accountable owner | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Least privilege | PROTECT | Access/audit logs and controlled negative-access test evidence | Verify unauthorised access is denied and relevant privileged activity is logged | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Email filtering | PROTECT | Email security design and configuration export | Verify anti-phishing, spoofing, URL and attachment protections are appropriately configured and enforcement actions are defined | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Email filtering | PROTECT | Block/quarantine logs for an appropriate review period | Verify the control has operated historically and inspect representative detections/quarantines | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Email filtering | PROTECT | User-reported phishing / false-negative investigation records | Assess messages that bypassed filtering and verify weaknesses are investigated and tuned/remediated | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Email filtering | PROTECT | Authorised controlled email-security test results | Verify representative test messages are handled as intended without relying solely on production phishing statistics | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Logging / suspicious-login alerts | DETECT | Payroll logging standard / requirements | Verify required authentication, MFA, privilege, sensitive-access and source-context events plus retention requirements are defined | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Logging / suspicious-login alerts | DETECT | Logging configuration, SIEM ingestion status and representative raw logs | Verify required sources are enabled, reaching the monitoring platform and retaining the expected event fields | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Logging / suspicious-login alerts | DETECT | Detection-rule definitions and representative alert evidence | Verify defined suspicious-login scenarios generate alerts as intended and rules are appropriately scoped | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Logging / suspicious-login alerts | DETECT | Alert triage / SOC case records | Verify alerts are assigned, investigated, dispositioned and escalated according to applicable response targets | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Incident-response procedure | RESPOND | To be developed | To be developed | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Tested backups / recovery | RECOVER | To be developed | To be developed | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Security policies / responsibilities | GOVERN | To be developed | To be developed | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Asset inventory / business-process mapping | IDENTIFY | To be developed | To be developed | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Payroll/phishing risk assessment | IDENTIFY | To be developed | To be developed | Not Tested — Lab |
