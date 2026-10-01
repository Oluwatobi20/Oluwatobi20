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
| R-01 | Credential phishing affecting payroll | Incident-response procedure | RESPOND | Current incident-response plan and payroll/credential-compromise playbook | Verify approved response procedures define relevant roles, containment, escalation and communications, and are reviewed according to policy | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Incident-response procedure | RESPOND | Roles/responsibilities, contact list and on-call/escalation arrangements | Verify accountable responders, required authorities, vendor contacts and deputies are defined and current | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Incident-response procedure | RESPOND | Tabletop / simulation report and remediation tracker | Verify the response process has been exercised, lessons identified and corrective actions tracked | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Incident-response procedure | RESPOND | Post-incident report or authorised simulated-incident record | Verify response actions were executed, evidenced and used to improve procedures where applicable | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Tested backups / recovery | RECOVER | Payroll recovery requirements / BIA with defined RTO and RPO | Verify recovery objectives are defined from business requirements and can be used as measurable recovery criteria | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Tested backups / recovery | RECOVER | Backup job configuration and success/failure logs for an appropriate review period | Verify payroll data is in scope, backups run as scheduled and failures are detected and addressed | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Tested backups / recovery | RECOVER | Backup isolation, immutability and access-control evidence | Verify backup copies are protected from compromise or deletion through appropriate isolation, credential separation and/or immutable/offline storage | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Tested backups / recovery | RECOVER | Documented payroll restoration test | Verify an actual restore can meet defined recovery objectives and that restored data is checked for integrity and usability | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Security policies / responsibilities | GOVERN | Approved payroll/security policy or governance charter | Verify security requirements, governance expectations, approval, ownership, review cycle and communication are formally established | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Security policies / responsibilities | GOVERN | RACI / accountability map and relevant role descriptions | Verify accountable system, data and risk ownership is formally assigned and understood | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Security policies / responsibilities | GOVERN | Relevant governance / risk committee minutes | Verify payroll cyber risks, control performance, exceptions and risk decisions receive appropriate management oversight | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Security policies / responsibilities | GOVERN | Risk decisions, exception approvals and remediation/action tracker | Verify management decisions are authorised, documented, assigned and tracked through resolution or accepted risk | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Asset inventory / business-process mapping | IDENTIFY | To be developed | To be developed | Not Tested — Lab |
| R-01 | Credential phishing affecting payroll | Payroll/phishing risk assessment | IDENTIFY | To be developed | To be developed | Not Tested — Lab |


## NIST CSF 2.0 Detailed Mapping — PR.AA-05

**Organisational control:** Payroll least-privilege and separation-of-duties access control  
**Function:** PROTECT (PR)  
**Category:** Identity Management, Authentication, and Access Control (PR.AA)  
**Subcategory:** PR.AA-05  
**Portfolio result:** Not Tested — Lab

### Evidence
- Payroll RBAC matrix: roles, permissions and business justification.
- Live payroll entitlements export plus relevant AD / Entra group-to-role mappings.
- Periodic access recertification evidence plus Joiner/Mover/Leaver records for the selected review period.
- Payroll separation-of-duties conflict matrix, including incompatible entitlements such as maintaining bank details and approving payments.

### Test Procedure
1. Compare selected users' live permissions with approved RBAC roles and investigate additional roles, privilege creep and unexplained entitlements.
2. Inspect access recertification evidence for genuine owner review and resulting removals/changes. Sample leavers and movers and compare completion times against the organisation's defined access-removal/change target.
3. Analyse live entitlements for defined SoD conflicts. Where authorised, test whether conflicting access is prevented or routed through an approved exception/compensating-control process.

### Assessment Criteria
- **PASS:** Tested access aligns with approved roles; review/JML controls operate as required; no unexplained SoD conflicts are identified, or conflicts are prevented/appropriately controlled.
- **PARTIAL:** The control generally operates but weaknesses such as delayed/incomplete review or appropriately documented compensating controls reduce assurance.
- **FAIL:** Material excessive or stale access exists, required leaver access remains active, or incompatible payroll capabilities can be exercised without required independent control.

> Sampling sizes and remediation timelines are determined by the assessment scope, population, risk and organisational policy rather than treated as universal NIST requirements.
