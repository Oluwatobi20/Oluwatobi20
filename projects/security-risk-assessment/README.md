# Project 1: Security Risk Assessment Lab

**Status:** In progress

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
| R-02 | To be assessed | | | | | | | | |
| R-03 | To be assessed | | | | | | | | |
| R-04 | To be assessed | | | | | | | | |
| R-05 | To be assessed | | | | | | | | |

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

This section will be completed as I perform the assessment. I will not mark the lab complete until I can explain and defend each risk decision myself.

## Learning outcomes

By completing this project I aim to demonstrate that I can:

- Distinguish an asset, threat, vulnerability and risk
- Apply confidentiality, integrity and availability concepts
- Select appropriate security controls
- Explain inherent and residual risk
- Choose an appropriate risk treatment
- Communicate security findings clearly

## Next step

Complete R-01 independently, beginning with one business asset and identifying a realistic threat and vulnerability.
