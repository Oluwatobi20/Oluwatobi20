# Project 1: Security Risk Assessment Lab

**Status:** Completed — assessment exercise

## Objective

Build a practical risk assessment using the security concepts I am studying for ISC2 Certified in Cybersecurity (CC). The completed project will demonstrate how I identify assets, threats and vulnerabilities, assess risk, recommend controls, and document risk treatment decisions.

## Scenario

This lab uses a fictional small UK business so that no real organisation or sensitive information is exposed.

The fictional company has:
- 25 employees
- Employee laptops
- A small office network and Wi-Fi
- Cloud email and file storage
- Customer and employee information
- Remote-working staff
- An administrator account used to manage business systems

## Method

For each scenario I will document:

1. Asset
2. Threat
3. Vulnerability
4. Potential impact
5. Likelihood
6. Risk level
7. Existing or proposed controls
8. Risk treatment: mitigate, avoid, transfer or accept
9. Residual risk

## Risk Register

| ID | Asset | Threat | Vulnerability | Impact | Likelihood | Risk | Recommended Control | Treatment | Residual Risk |
|---|---|---|---|---|---|---|---|---|---|
| R-01 | Human Resources payroll system (stated value: £16k of data) | Phishing email with malicious link | Staff have not had phishing training and MFA is not enabled, allowing stolen credentials to be used to access the system | High — sensitive payroll/personal data; fraud, operational, legal and reputational consequences | High — phishing exposure combined with weak authentication and limited awareness controls | High | MFA; email filtering and DMARC; security awareness training; strong password policy/SSO; least privilege; logging and alerting; incident response plan; encrypted recoverable backups | Mitigate | Low/Medium target, subject to validation after controls are implemented |
| R-02 | Company employee laptops (25 endpoints) and data/access available through them | Physical theft, loss or unauthorised access in public remote-working locations | Devices may be left unattended; potential gaps in auto-lock, full-disk encryption, remote-working policy, awareness training and MDM | High — potential data exposure, loss of access, operational disruption and compromise of connected services | High — scenario assumes repeated insecure behaviour in public locations across a mobile endpoint fleet | High | Full-disk encryption; enforced screen lock; MDM/remote-wipe capability; MFA for company resources; least privilege; physical safeguards; browser credential controls; remote-working policy; awareness training; rapid incident reporting | Mitigate | Low/Medium target, subject to implementation and control-effectiveness validation |
| R-03 | Finance endpoint, credentials, shared company file storage and connected backup repository | Suspected ransomware following a malicious/spoofed supplier attachment | Potential gaps in attachment controls, macro/script restrictions, endpoint detection, least privilege, segmentation and backup isolation | Critical/High — widespread encryption could disrupt operations and recovery; confidentiality impact depends on evidence of exfiltration | High — under the scenario assumptions, malicious execution plus broad write access and connected backups creates substantial exposure | Critical | Immediate network containment; preserve evidence; protect backups; email/attachment controls; macro restrictions; EDR; least privilege/RBAC; segmentation; offline/immutable backups; awareness and restore testing | Mitigate + incident containment | Low/Medium target, subject to successful recovery testing and control validation |
| R-04 | Finance, customer and commercial data; company endpoint containing the downloaded copy | Potential insider data collection or exfiltration during notice period; intent unconfirmed | Possible excessive permissions, weak leaver controls, limited DLP/data classification and insufficient behavioural monitoring | High — potential personal-data, commercial, contractual and operational consequences if data is misused or leaves company control | Medium — anomalous bulk access warrants investigation, but no external transfer or malicious intent is established | High | Preserve and review logs; validate business justification; investigate transfer channels; coordinate proportionate access decisions with HR/management; strengthen leaver workflow, least privilege, DLP and data classification | Mitigate | Low/Medium target, subject to control validation and reassessment |
| R-05 | Company endpoints, data and privileged third-party remote-access path | Potential supply-chain compromise using a compromised TechAssist technician account | Password-only third-party authentication, shared supplier identity, persistent privileged access, limited approval/alerting, and lack of formal supplier security review | Critical/High — privileged remote access could enable endpoint compromise, credential theft, lateral movement, disruption or data exposure | High — confirmed remote sessions from a known-compromised account create a serious investigation threshold, though malicious activity on endpoints remains unconfirmed | Critical | Suspend/restrict supplier access; isolate and investigate the three affected endpoints; preserve logs; rotate exposed privileged credentials as appropriate; enterprise threat hunt; implement MFA, named identities, PAM/JIT access, least privilege, monitoring and third-party governance | Mitigate + contain | Low/Medium target, subject to forensic findings and control validation |

## R-01 Assessment Rationale

### Impact — High

The payroll system contains sensitive employee and financial information. A compromise could affect all three elements of the CIA triad:

- **Confidentiality:** exposure of names, addresses, National Insurance numbers, salary and banking information.
- **Integrity:** unauthorised changes to payroll or bank details could enable salary diversion and fraud.
- **Availability:** deletion, ransomware or account lockout could disrupt payroll and prevent staff being paid.

The scenario may also create financial, legal/regulatory and reputational consequences.

### Likelihood — High (current scenario)

The scenario assumes weak authentication and limited user awareness: MFA is not enabled and staff have not received phishing training. A successful credential-phishing attempt could therefore lead directly to account access. The rating should be reviewed after controls are implemented and tested.

### Overall risk — High

Using this lab's qualitative Low/Medium/High model, High Impact combined with High Likelihood is assessed as **High Risk**.

### Treatment — Mitigate

The selected treatment is mitigation because the business needs payroll and email services, while security controls can reduce the likelihood and/or impact of compromise.

### Proposed defence-in-depth controls

**Reduce likelihood:** MFA; email filtering and DMARC; recurring security-awareness training and phishing exercises; strong password policy, password manager and SSO where appropriate.

**Reduce impact:** least-privilege access; separate privileged/admin accounts; logging and alerts for unusual access, bulk downloads and sensitive payroll changes.

**Recovery and response:** documented incident-response procedures and tested, encrypted backups with appropriate separation from production systems.

### Residual risk

Target residual risk is **Low/Medium**, but this is not claimed as achieved until the controls have actually been implemented, tested and the risk reassessed.

## R-02 Assessment Rationale

**Title:** Physical Loss / Theft of Endpoint from Insecure Remote Working (Café)

### Asset

The scope is the company's 25 employee laptops and the business information or authenticated access available through them, including local files, cached communications, browser sessions/credentials and remote access to company services.

### Threat

Opportunistic physical theft, device loss and subsequent unauthorised access. The scenario also considers visual exposure or unauthorised interaction when a device is left unattended in a public location.

### Vulnerabilities / control gaps

The assessment identifies compounding weaknesses: repeated unattended-device behaviour; possible gaps in enforced screen locking and full-disk encryption; inadequate remote-working policy or awareness; absence of privacy safeguards; and lack of centrally managed device controls such as MDM and remote-wipe capability.

### Impact — High

Potential consequences include confidentiality loss if business or personal data is exposed, integrity risk if an authenticated session is abused, operational disruption while the endpoint is replaced/recovered, and possible access to connected company services. Regulatory consequences depend on the actual data exposed and circumstances of an incident.

### Likelihood — High (current scenario)

The scenario assumes repeated unattended use in public locations and a fleet of mobile endpoints. The High rating reflects those scenario assumptions rather than a claim about a measured annual theft probability.

### Inherent risk — High

Using this lab's qualitative matrix, High Impact combined with High Likelihood is assessed as **High inherent risk**.

### Treatment — Mitigate

Remote work is a business requirement in this scenario, so the recommended response is to reduce risk through defence-in-depth controls.

### Proposed controls

**Technical:** enforce full-disk encryption; centrally enforce automatic screen locking; use managed endpoint/MDM capabilities including remote response where supported; require MFA for company resources; remove unnecessary local administrator rights; and control storage of credentials/browser sessions.

**Physical:** provide appropriate privacy screens and physical security options where useful, while requiring staff to keep devices under their control in public.

**Administrative:** establish a remote-working security policy; provide targeted security-awareness training; maintain an asset inventory; and require immediate reporting of lost or stolen devices so IT can revoke sessions/credentials and begin incident response.

### Residual risk

The target residual risk is **Low/Medium**. This is a target, not an achieved rating. Full-disk encryption and access controls primarily reduce the consequences of a stolen device; they do not necessarily make the physical theft itself less likely. Residual risk should be reassessed after implementation and testing, with management determining whether it falls within the organisation's risk appetite.

### Analyst recommendation

Prioritise full-disk encryption, managed endpoint controls, MFA, least privilege and a clear lost-device response process, then validate deployment across all 25 endpoints before accepting the residual risk.

## R-03 Active Incident Assessment

**Title:** Suspected Ransomware Outbreak Following Malicious Excel Attachment — Finance  
**Status:** Incident in progress (lab scenario)  
**Classification:** Critical

### Initial diagnosis

The observed sequence — opening an unexpected/suspicious spreadsheet followed by files becoming inaccessible and filenames changing — is consistent with a **suspected ransomware incident**. The exact malware family, execution mechanism, supplier-spoofing method and whether data was exfiltrated are **not yet confirmed** and require investigation.

### First response — contain

The immediate priority is to isolate the affected endpoint from network connectivity to limit further spread or encryption of accessible network resources. The incident-response process should be activated and the organisation's evidence-preservation procedures followed. Whether a device should remain powered on or be shut down depends on the incident-response plan, available expertise and circumstances; preservation of volatile evidence must be balanced against continued malicious activity.

The connected backup repository and shared storage should be protected from the suspected compromise, while avoiding unnecessary destruction of evidence. Credentials/sessions associated with the affected account should be contained according to the response plan.

### Assets at risk

- Finance employee endpoint and authenticated sessions/credentials.
- Shared company storage accessible to that account, including Finance/Accounts and any other authorised shares.
- Connected backup infrastructure.
- Business information accessible through those systems.

### Threat and vulnerabilities

The working hypothesis is malicious code delivered through a deceptive attachment. Possible control gaps include insufficient attachment filtering/sandboxing, weak macro or script restrictions, inadequate endpoint detection, excessive share permissions, limited segmentation, and a backup repository that is continuously reachable from production.

### Impact — Critical/High

Potential consequences include widespread loss of availability through encryption, operational downtime, recovery costs and integrity concerns. Confidentiality impact should not be assumed solely from encryption; evidence of data access or exfiltration must be investigated. Regulatory consequences depend on whether personal data was compromised and the resulting risk to individuals.

### Likelihood — High (scenario assessment)

The High rating reflects the scenario's assumed control weaknesses and observed execution of suspicious activity. Unsupported numerical or industry-ranking claims are not used to justify the rating.

### Inherent risk — Critical

Under this lab's qualitative model, the combination of Critical/High impact and High likelihood is treated as **Critical inherent risk** requiring urgent response.

### Treatment — Mitigate and contain

**Immediate:** isolate affected systems; activate incident response; protect backup and shared-storage recovery options; preserve relevant evidence; investigate the scope; contain compromised identities/sessions; and determine whether other endpoints or servers show indicators of compromise.

**Short term:** strengthen email/attachment controls; restrict untrusted macros/scripts; deploy and tune endpoint detection/response; enforce least privilege and role-based share access; and improve backup isolation/immutability.

**Longer term:** improve segmentation where justified, conduct targeted phishing/supplier-invoice awareness exercises, test restoration regularly, and rehearse the ransomware incident-response plan.

### Backup resilience

Backups should be designed so that compromise of production credentials or systems cannot automatically destroy all recovery copies. The organisation should maintain appropriately separated/offline or immutable recovery copies and regularly verify that restoration actually works.

### Residual risk

Target residual risk is **Low/Medium**, but it is not considered achieved until preventive controls are implemented, recovery is tested, and the organisation reassesses both likelihood and business impact.

### Analyst recommendation

Treat the event as a serious suspected ransomware incident until investigation establishes otherwise. Prioritise containment, preservation of viable recovery copies, scope determination and tested recovery. Purchasing decisions and exact recovery objectives should follow validated technical and business requirements rather than unverified cost assumptions.

## R-04 Potential Insider Data Collection Assessment

**Title:** Potential Insider Data Collection During Notice Period — Finance  
**Status:** Alert triaged — under investigation (lab scenario)  
**Handling:** Confidential — need-to-know

### Facts established by the scenario

- The Finance employee has six years' tenure and is due to leave on Friday.
- Approximately 8 GB was downloaded from Finance, customer and commercial folders to the company laptop on Wednesday evening.
- The employee is authorised to access some, but not all, of the relevant folders in the normal course of work.
- The scenario provides no evidence that the data has been transferred to a personal device, personal cloud service, email account or other external destination.
- No malicious intent has been established.

### Hypotheses — not findings

Possible explanations include legitimate handover/offline work, accidental or mistaken over-collection, a non-malicious policy breach, or intentional data collection/exfiltration. These hypotheses should guide evidence collection without being treated as conclusions.

### Questions to investigate

Determine what data was downloaded and its sensitivity; whether management requested or expected the activity; whether the files were transferred externally; whether comparable downloads are normal for this user; and whether access to folders outside the employee's role reflects excessive permissions or another authorised business purpose.

### Assets

Finance records, customer information, commercial information/intellectual property, and the company-managed endpoint holding the local copy.

### Threat

Potential insider-related unauthorised collection, disclosure or exfiltration. The actor's intent remains unknown, so accidental, negligent and deliberate scenarios remain open until evidence supports narrowing the assessment.

### Vulnerabilities / control gaps

Potential gaps include over-provisioned permissions, weak leaver/access-review processes, insufficient data classification and DLP controls, and inadequate monitoring/baselining of unusual access patterns.

### Impact — High

If sensitive customer or commercial information leaves authorised company control, consequences could include privacy, contractual, financial and competitive harm. Regulatory obligations depend on the data involved, whether a personal-data breach actually occurred and the risk created for affected individuals.

### Likelihood — Medium

The anomalous volume, timing and access outside normal scope justify investigation. The rating remains Medium because neither malicious intent nor external exfiltration has been established. Unsupported industry percentages are not used.

### Inherent risk — High

Under the lab's qualitative matrix, High Impact combined with Medium Likelihood is assessed as **High inherent risk**.

### Immediate actions

Preserve relevant audit, endpoint, identity and network evidence; identify the files and sensitivity involved; check authorised telemetry for evidence of external transfer; confirm with the line manager whether the activity had a legitimate business purpose; and coordinate any access restriction or employment-related action with appropriate HR/management/legal stakeholders.

Containment should be proportionate to evidence and risk. The security team should not assume that leaving an account active until the final day is inherently required, nor that reducing access is punitive: access decisions should follow business need, established policy and the organisation's response process.

### Treatment — Mitigate

Recommended longer-term controls include a formal joiner/mover/leaver process, role-based access and periodic entitlement reviews, proportionate DLP controls, data classification, appropriate monitoring of anomalous access, restrictions on unauthorised removable media/personal cloud where justified, and clear confidentiality/data-return expectations during offboarding.

Thresholds such as a fixed 1 GB DLP limit should be tuned to normal business behaviour rather than assumed to be universally appropriate.

### Residual risk

Target residual risk is **Low/Medium**, subject to implementation, testing and reassessment. Controls primarily reduce likelihood and exposure; the inherent business impact of losing genuinely sensitive information may remain High even after strong preventive controls are introduced.

### Analyst recommendation

Investigate the alert objectively and proportionately. Preserve evidence, establish the business context and determine whether any data actually left company control before drawing conclusions about intent or misconduct. Escalation should follow the evidence and the organisation's incident, HR and legal processes.

## R-05 Third-Party / Supply-Chain Assessment

**Title:** Suspicious Remote Access by Compromised Supplier Account — TechAssist Ltd  
**Status:** Active security incident investigation (lab scenario)  
**Handling:** Restricted / need-to-know

### What is known

TechAssist has privileged remote-management access to the company's 25 endpoints. TechAssist reported that one technician account was compromised and stated that it had no evidence customer systems were accessed. Company telemetry independently records remote sessions from that account to three company endpoints at 02:17 Sunday. No malware installation, persistence, data exfiltration or destructive activity has yet been confirmed.

The supplier account uses password-only authentication, is used across multiple customer environments, has persistent remote administrative capability, and does not generate an automatic company security alert when used.

### What remains unknown

Investigation must establish what occurred during the three sessions, whether the sessions were legitimate or attacker-controlled, whether commands/files/configuration changes occurred, whether persistence or credential access occurred, whether additional company systems were reached, and how TechAssist scoped its own investigation.

### Assets

The assets include the 25 company endpoints, the three endpoints with recorded remote sessions, company information and authenticated resources accessible from those endpoints, and the privileged third-party management channel itself.

### Threat

The working threat scenario is abuse of a trusted third-party remote-management identity following compromise of the supplier account. This represents a potential third-party/supply-chain intrusion path. It does not, by itself, establish that the three endpoints were successfully compromised.

### Vulnerabilities / control gaps

Potential gaps include password-only privileged authentication; shared rather than individually attributable supplier identities; persistent 24/7 privileged access; excessive standing privilege; lack of connection approval/notification; insufficient supplier-security assurance; and inadequate monitoring of third-party privileged sessions.

### Impact — Critical/High

If privileged sessions were attacker-controlled, local administrative rights could enable significant endpoint modification, security-control interference, credential access and further movement. Confidentiality, integrity and availability consequences depend on what actions actually occurred and what other resources were reachable. Any privacy/regulatory assessment must be based on evidence of personal-data compromise and the applicable obligations rather than assumed automatically.

### Likelihood — High (investigation priority)

The High rating reflects the combination of TechAssist's confirmed account compromise and company logs showing sessions from that identity. It does **not** mean malicious endpoint compromise has been proven.

### Inherent risk — Critical

Within this lab's qualitative matrix, Critical/High potential impact combined with High likelihood/exposure is treated as **Critical inherent risk** requiring urgent containment and investigation. This is not ranked against the other portfolio risks because different scenarios are not directly comparable without a common quantitative methodology.

### Immediate actions

Temporarily suspend or tightly restrict the affected supplier access path; isolate the three endpoints where proportionate; preserve remote-management, endpoint, identity and network telemetry; establish what actions occurred during the sessions; review the wider estate for related indicators; and rotate/revoke credentials or sessions that investigation shows may have been exposed. Coordinate containment with management and TechAssist without allowing the supplier's investigation to substitute for the company's own evidence.

### Treatment — Mitigate and contain

The organisation should replace standing supplier privilege with controlled access. Recommended controls include MFA for privileged third-party identities, individually attributable technician accounts, least privilege, privileged-access management and just-in-time/time-bounded elevation, explicit connection approval where practical, comprehensive session logging/alerting, and an appropriately segmented management path.

Third-party governance should define security requirements, incident-notification obligations, evidence/cooperation expectations, access reviews and proportionate assurance. Specific certifications or notification deadlines should be selected based on the organisation's requirements and contract rather than assumed universally mandatory.

### Residual risk

Target residual risk is **Low/Medium**, subject to investigation results, implementation and testing. MFA and JIT access can substantially reduce exposure, but the potential impact of compromise through a genuinely privileged supplier channel may remain significant. Residual risk therefore requires periodic reassessment.

### Management response

TechAssist's statement that it has no evidence customer systems were accessed is relevant but does not resolve the company's own telemetry showing three remote sessions. Management should not treat either supplier compromise of the endpoints or endpoint safety as proven without investigation.

Business continuity can be maintained proportionately while the affected access path and endpoints are contained and investigated. Decisions about the remaining endpoints should follow evidence from the threat hunt and the organisation's incident-response process.

### Analyst recommendation

Treat the three recorded sessions as a high-priority security investigation. Contain the trusted remote-access path, determine exactly what occurred, preserve evidence, assess the wider estate, and restore supplier access only under appropriately strengthened authentication, privilege and monitoring controls.

## Security controls to consider

- Administrative controls
- Technical controls
- Physical controls
- Preventive controls
- Detective controls
- Corrective controls
- Multi-factor authentication
- Principle of least privilege
- Separation of duties
- Backups and recovery
- Security policies and procedures

## Evidence

This assessment exercise now contains five completed risk scenarios. Proposed controls and residual-risk ratings are analytical recommendations within the fictional lab; they do not represent controls deployed in a real organisation.

## Learning outcomes

By completing this project I aim to demonstrate that I can:

- Distinguish an asset, threat, vulnerability and risk
- Apply confidentiality, integrity and availability concepts
- Select appropriate security controls
- Explain inherent and residual risk
- Choose an appropriate risk treatment
- Communicate security findings clearly

## Project completion

Completed scenarios: R-01 credential phishing/payroll risk; R-02 physical endpoint loss/theft; R-03 suspected ransomware incident; R-04 potential insider data collection; and R-05 third-party/supply-chain compromise. The next portfolio project will move from qualitative risk analysis into a hands-on network security lab.
