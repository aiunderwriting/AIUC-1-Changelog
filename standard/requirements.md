# Requirements

## A001: Establish input data policy

Establish and communicate AI input data policies covering how customer data is used for model training, inference processing, data retention periods, and customer data rights

---

## A002: Establish output data policy

Establish AI output ownership, usage, opt-out and deletion policies to customers and communicate these policies

---

## A003: Limit AI agent data collection

Implement safeguards to limit AI agent data access to task-relevant information based on user roles and context

---

## A004: Protect IP & trade secrets

Implement safeguards or technical controls to prevent AI systems from leaking company intellectual property or confidential information

---

## A005: Prevent cross-customer data exposure

Implement safeguards to prevent cross-customer data exposure when combining customer data from multiple sources

---

## A006: Prevent PII leakage

Establish safeguards to prevent personal data leakage through AI outputs and logs

---

## A007: Prevent IP violations

Implement safeguards and technical controls to prevent AI outputs from violating copyrights, trademarks, or other third-party intellectual property rights

---

## B001: Third-party testing of adversarial robustness

Implement adversarial testing program to validate system resilience against adversarial inputs and prompt injection attempts in line with adversarial threat taxonomy

---

## B002: Detect adversarial input

Implement monitoring capabilities to detect and respond to adversarial inputs and prompt injection attempts

---

## B003: Manage public release of technical details

Implement controls to prevent over-disclosure of technical information about AI systems and organizational details that could enable adversarial targeting

---

## B004: Prevent AI endpoint scraping

Implement safeguards to prevent probing or scraping of external AI endpoints

---

## B005: Implement real-time input filtering

Implement real-time input filtering using automated moderation tools

---

## B006: Prevent unauthorized AI agent actions

Implement safeguards to prevent AI agents from performing actions beyond intended scope and authorized privileges

---

## B007: Enforce user access privileges to AI systems

Establish and maintain user access controls and admin privileges for AI systems in line with policy

---

## B008: Protect model deployment environment

Implement security measures for AI model deployment environments including encryption, access controls and authorization

---

## B009: Limit output over-exposure

Implement output limitations and obfuscation techniques to safeguard against information leakage

---

## C001: Define AI risk taxonomy

Establish a risk taxonomy that categorizes risks within harmful, out-of-scope, and hallucinated outputs, tool calls, and other risks based on application-specific usage

---

## C002: Conduct pre-deployment testing

Conduct internal testing of AI systems prior to deployment across risk categories for system changes requiring formal review or approval

---

## C003: Prevent harmful outputs

Implement safeguards or technical controls to prevent harmful outputs including distressed outputs, angry responses, high-risk advice, offensive content, bias, and deception

---

## C004: Prevent out-of-scope outputs

Implement safeguards or technical controls to prevent out-of-scope outputs (e.g. political discussion, healthcare advice)

---

## C005: Prevent customer-defined high risk outputs

Implement safeguards or technical controls to prevent additional high risk outputs as defined in risk taxonomy

---

## C006: Prevent output vulnerabilities

Implement safeguards to prevent security vulnerabilities in outputs from impacting users

---

## C007: Flag high risk outputs

Implement an alerting system that flags high-risk outputs for human review

---

## C008: Monitor AI risk categories

Implement monitoring of AI systems across risk categories

---

## C009: Enable real-time feedback and intervention

Implement mechanisms to enable real-time user feedback collection and intervention mechanisms

---

## C010: Third-party testing for harmful outputs

Appoint expert third parties to evaluate system robustness to harmful outputs including distressed outputs, angry responses, high-risk advice, offensive content, bias, and deception at least every 3 months

---

## C011: Third-party testing for out-of-scope outputs

Appoint expert third parties to evaluate system robustness to out-of-scope outputs at least every 3 months (e.g. political discussion, healthcare advice)

---

## C012: Third-party testing for customer-defined risk

Appoint expert third-parties to evaluate system robustness to additional high-risk outputs as defined in risk taxonomy at least every 3 months

---

## D001: Prevent hallucinated outputs

Implement safeguards or technical controls to prevent hallucinated outputs

---

## D002: Third-party testing for hallucinations

Appoint expert third-parties to evaluate hallucinated outputs at least every 3 months

---

## D003: Restrict unsafe tool calls

Implement safeguards or technical controls to prevent tool calls in AI systems from executing unauthorized actions, accessing restricted information, or making decisions beyond their intended scope

---

## D004: Third-party testing of tool calls

Appoint expert third-parties to evaluate tool calls in AI systems, including executing unauthorized actions, accessing restricted information, or making decisions beyond their intended scope at least every 3 months

---

## E001: AI failure plan for security breaches

Document AI failure plan for AI privacy and security breaches assigning accountable owners and establishing notification and remediation with third-party support as needed (e.g. legal, PR, insurers)

---

## E002: AI failure plan for harmful outputs

Document AI failure plan for harmful AI outputs that cause significant customer harm assigning accountable owners and establishing remediation with third-party support as needed (e.g. legal, PR, insurers)

---

## E003: AI failure plan for hallucinations

Document AI failure plan for hallucinated AI outputs that cause substantial customer financial loss assigning accountable owners and establishing remediation with third-party support as needed (e.g. legal, PR, insurers)

---

## E004: Assign accountability

Document which AI system changes across the development & deployment lifecycle require formal review or approval, assign a lead accountable for each, and document their approval with supporting evidence

---

## E005: Assess cloud vs on-prem processing

Establish criteria for selecting cloud provider, and circumstances for on-premises processing considering data sensitivity, regulatory requirements, security controls, and operational needs

---

## E006: Conduct vendor due diligence

Establish AI vendor due diligence processes for foundation and upstream model providers covering data handling, PII controls, security and compliance

---

## E007: [Retired] Document system change approvals

Merged with E004 - see changelog (Q1 2026 update)

---

## E008: Review internal processes

Establish regular internal reviews of key processes and document review records and approvals

---

## E009: Monitor third-party access

Implement systems to monitor third party access

---

## E010: Establish AI acceptable use policy

Establish and implement an AI acceptable use policy

---

## E011: Record processing locations

Document AI data processing locations

---

## E012: Document regulatory compliance

Document applicable AI laws and standards, required data protections, and strategies for compliance

---

## E013: Implement quality management system

Establish a quality management system for AI systems proportionate to the size of the organization

---

## E014: Share transparency reports

Merged with E017 - see changelog (Q1 2026 update)

---

## E015: Log model activity

Maintain logs of AI system processes, actions, and model outputs where permitted to support incident investigation, auditing, and explanation of AI system behavior

---

## E016: Implement AI disclosure mechanisms

Implement clear disclosure mechanisms to inform users when they are interacting with AI systems rather than humans

---

## E017: Document system transparency policy

Establish a system transparency policy and maintain a repository of model cards, datasheets, and interpretability reports for major systems

---

## F001: Prevent AI cyber misuse

Implement or document guardrails to prevent AI-enabled misuse for cyber attacks and exploitation

---

## F002: Prevent catastrophic misuse

Implement or document guardrails to prevent AI-enabled catastrophic system misuse (chemical / bio / radio / nuclear)

---

