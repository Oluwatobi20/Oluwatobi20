# Project 2: GRC Controls & Framework Mapping

**Status:** In Progress  
**Analyst:** Oluwatobi Oyero  
**Environment:** Fictional business scenario / portfolio exercise  
**Primary Framework:** NIST Cybersecurity Framework (CSF) 2.0

## Objective

Demonstrate how a GRC analyst connects identified cybersecurity risks to security controls, maps those controls to recognised framework outcomes, defines appropriate evidence, and evaluates control design, implementation and operating effectiveness.

This project builds on the completed Security Risk Assessment Lab. It does not claim that controls were tested in a real organisation.

## Skills Demonstrated

- Risk-to-control mapping
- NIST CSF 2.0 function mapping
- Control rationale
- Control evidence requirements
- Control design and implementation assessment
- Operating-effectiveness testing concepts
- Identification of control gaps
- Remediation and residual-risk thinking

## NIST CSF 2.0 Functions

The project uses the six CSF 2.0 Functions:

**GOVERN → IDENTIFY → PROTECT → DETECT → RESPOND → RECOVER**

## R-01: Payroll Credential-Phishing Risk

### Function-Level Control Mapping

| Control / Activity | Primary CSF Function | Rationale |
|---|---|---|
| Security policies assigning responsibilities | GOVERN | Establishes security expectations, accountability, roles and oversight for the controls protecting payroll. |
| Payroll asset inventory and business-process mapping | IDENTIFY | Documents the payroll system, information it processes, where it resides and who requires access so the organisation understands what it must protect. |
| Payroll/phishing risk assessment | IDENTIFY | Assesses the likelihood and impact of credential theft affecting payroll so management can prioritise appropriate controls. |
| Multi-Factor Authentication (MFA) | PROTECT | Requires an additional authentication factor so a phished password alone should not be sufficient to access payroll. |
| Security-awareness / phishing training | PROTECT | Reduces phishing exposure by teaching staff to recognise and report suspicious messages before providing credentials. |
| Least-privilege access | PROTECT | Limits account permissions so compromise of an ordinary account does not automatically provide unnecessary privileged payroll access. |
| Email filtering | PROTECT | Blocks or quarantines suspicious messages before they reach users where technically possible. |
| Logging and suspicious-login alerts | DETECT | Helps identify anomalous authentication activity such as unusual locations, times or access patterns. |
| Incident-response procedure | RESPOND | Defines responsibilities and actions for containing, investigating, eradicating and communicating a confirmed or suspected credential compromise. |
| Tested backups and recovery | RECOVER | Supports restoration of payroll services/data following destructive activity or other recoverable disruption. |

> A control may support more than one CSF Function. This table identifies the primary Function for the purpose of this portfolio exercise.

## MFA Control Evidence & Testing Matrix

**Management assertion:** “We have MFA, so R-01 is controlled.”

A GRC assessment should verify the assertion rather than treating the existence of an MFA policy or product as proof of control effectiveness.

| Evidence Requested | Purpose / Test Objective | Control Aspect |
|---|---|---|
| Payroll authentication configuration screenshot or IAM policy export | Verify MFA is enforced for all in-scope payroll authentication paths rather than merely available or optional. | Design / Implementation |
| MFA enrolment report from the identity provider | Verify the population required by the control is enrolled and identify/investigate exceptions. | Implementation / Coverage |
| Authentication logs showing MFA challenges, successes and failures | Verify the control has operated during actual authentication activity over an appropriate review period. | Operating Effectiveness |
| Documented access test using a valid password without the required second factor | Confirm password-only authentication is denied for an in-scope payroll access attempt. | Operating Effectiveness |

### Assessment Principle

**“The organisation has MFA” is a management assertion.**

Configuration evidence, population evidence, authentication logs and testing provide evidence that a GRC analyst can use to evaluate whether the control is appropriately designed, implemented and operating as intended.

## Control Assessment Model

For subsequent controls, this project will consider:

1. **Design** — Is the control capable of addressing the stated risk?
2. **Implementation** — Has the control actually been deployed across the required scope?
3. **Operating Effectiveness** — Is the control consistently operating as intended over time?
4. **Exceptions** — Are there approved or unexplained deviations from the required control?
5. **Evidence** — Is there sufficient, appropriate evidence to support the assessment?
6. **Remediation** — If a gap exists, what action, owner and target date are required?

## Next Phase

Map selected R-01 controls to NIST CSF 2.0 Categories and Subcategories, then expand the matrix to selected ISO/IEC 27001 control areas. Findings will remain labelled as portfolio/lab assessments unless supported by evidence from an authorised real environment.
