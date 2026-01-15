# Controls

## A001: Establish input data policy

### Control shoulds
- Defining and communicating input data usage policies. Including specifying how customer data is used for inference and model training, establishing data retention periods, and documenting customer data rights.
- Implementing technical controls to enforce data retention and deletion policies. For example, automating data deletion based on retention schedules, using secure removal mechanisms, and managing data lifecycles.

### Control mays
- Documenting processes for handling end-user data subject rights. For example, handling requests for opt-in/opt-out rights, access, portability, or deletion of input data.
---

## A002: Establish output data policy

### Control shoulds
- Establishing output ownership and usage rights policies. For example, specifying customer ownership of AI-generated outputs versus AI inputs, defining permitted uses of outputs (commercial use, redistribution, modification), documenting usage restrictions or limitations, and clarifying how ownership applies to different output types or use cases.
- Disclosing opt-out and deletion procedures for AI outputs. For example, documenting how customers can opt out of output storage or reuse, explaining deletion request processes, specifying retention periods and data handling practices, and clarifying how customers can control or revoke permissions for their outputs.
---

## A003: Limit AI agent data collection

### Control shoulds
- Configuring data collection limits to reduce data and privacy exposure. For example, limiting data collection to task-relevant information based on context, implementing scoping based on user roles or workflow requirements, and avoiding persistent or out-of-scope data access.

### Control mays
- Deploying monitoring mechanisms. Including ensuring AI systems only perform necessary inference and logging deviations from defined operational scope.
- Integrating with existing authorization systems to align agent access permissions with organizational policies.
---

## A004: Protect IP & trade secrets

### Control shoulds
- Providing user guidance on protecting confidential information. For example, instructing employees not to input trade secrets, proprietary code, or confidential business information into AI systems, communicating data handling policies for AI tool usage, or establishing clear guidelines on what information can and cannot be shared with AI agents.

### Control mays
- Leveraging foundation model provider protections. For example, using providers with zero data retention policies, requiring contractual commitments that inputs are not used for training, selecting models with enhanced privacy guarantees for sensitive use cases.
- Implementing technical controls to detect proprietary information in outputs.
- Establishing output monitoring for high-risk IP scenarios. For example, logging AI responses that accessed confidential data sources, implementing human review workflows for outputs flagged as potentially containing sensitive information.
---

## A005: Prevent cross-customer data exposure

### Control shoulds
- Establishing explicit consent and disclosure for combined data usage. For example, informing customers when their data will be combined with competitor data, disclosing data anonymization and abstraction policies, providing opt-out mechanisms.
- Implementing customer data isolation controls. For example, enforcing strict logical and physical separation of customer data, applying tenant-specific encryption, validating data flow boundaries in shared infrastructure, establishing technical barriers between customer datasets during training.

### Control mays
- Implementing specific privacy-enhancing technologies (PETs) to reduce competitive exposure.
---

## A006: Prevent PII leakage

### Control shoulds
- Implementing safeguards to prevent personal data leakage through AI system outputs and logs. For example, filtering prompts and outputs for personal identifiers before storage or display, implementing automated PII detection and redaction in system logs, preventing retention of outputs containing sensitive personal information, or blocking responses that would expose personal identifiers.
- Requiring authentication and authorization for PII access. For example, role-based access controls for PII-containing systems, multi-factor authentication for sensitive data access, or approval-gated access to customer information.

### Control mays
- Integrating with existing data loss prevention (DLP) systems to monitor and block outputs containing personal data in violation of policy.
---

## A007: Prevent IP violations

### Control shoulds
- Documenting foundation model provider IP protections which may serve as primary infringement safeguards. For example, indemnification clauses or copyright/trademark guardrails.

### Control mays
- Establishing supplementary content filtering mechanisms where provider protections have gaps or limitations. For example, detecting copyrighted material in outputs, implementing trademark screening.
- Implementing user guidance and guardrails to reduce IP risk. For example, usage policies that explain prohibited content types, user warnings in product, restricting output generation in known infringement domains.
- Implementing restrictions in AI acceptable use policy.
---

## B001: Third-party testing of adversarial robustness

### Control shoulds
- Establishing a taxonomy for adversarial risks. For example, drawing on NIST's AI 100-2e2023 attack classifications and aligning these to system architecture and use cases.
- Conducting comprehensive adversarial testing at least quarterly. For example, performing structured red-teaming, prompt injection assessments, jailbreaking attempts, adversarial perturbation testing, semantic manipulation, and simulated malicious tool invocations.
- Maintaining secure testing documentation. For example, recording test cases, methods, outcomes, and system behaviors with restricted access controls, implementing secure storage for sensitive testing materials.
- Establishing improvement processes based on findings. For example, assigning owners and remediation timelines based on test severity, tracking fixes through risk registers or issue management systems, documenting updates to safeguards and procedures.

### Control mays
- Aligning adversarial testing with broader security testing programs. For example, integrating AI-specific test cases into broader penetration testing, sharing threat models across red/blue teams, aligning test cycles with security audit and compliance calendars.
---

## B002: Detect adversarial input

### Control shoulds
- Establishing detection and alerting. For example, implementing monitoring for prompt injection patterns, jailbreak techniques, adversarial input attempts, and exceeding rate limits, configuring alerts and threat notifications for suspicious activities.
- Implementing incident logging and response procedures. For example, logging suspected adversarial attacks with relevant context, escalating to designated personnel based on severity, and documenting response actions in a centralized system.
- Maintaining detection effectiveness through quarterly reviews. For example, updating detection rules based on emerging adversarial techniques, analyzing incident patterns and documenting system improvements.

### Control mays
- Implementing adversarial input detection prior to AI model processing where feasible. For example, using pre-processing filters to flag likely threats before model processing.
- Integrating adversarial input detection into existing security operations tooling. For example, forwarding flagged inputs to SIEM platforms, correlating detection with authentication and network logs, enabling SOC teams to triage AI-related security events.
---

## B003: Manage public release of technical details

### Control shoulds
- Documenting limitations on technical information release. For example, limiting public disclosure of model architectures, algorithms, training data details, system configurations, and performance metrics, requiring approval before sharing technical specifications or implementation details.
- Controlling organizational information to balance transparency with security. For example, limiting disclosure of AI team details, development timelines, and other information that could reveal technical capabilities, reviewing public communications for sensitive information.

### Control mays
- Establishing approval processes. For example, requiring designated review for public content referencing AI capabilities in e.g. publications, presentations, and marketing materials, and documenting approved disclosures with business justification.
---

## B004: Prevent AI endpoint scraping

### Control shoulds
- Implementing systems distinguishing between high-volume legitimate usage and adversarial behavior. For example, using behavioral analytics and user profiling to calibrate detection thresholds and prevent false positives against trusted users.
- Implementing rate limiting and query restrictions. For example, establishing per-user quotas to prevent model extraction, blocking excessive query patterns, implementing progressive restrictions for suspicious behavior, or using economic disincentives for high-volume usage.
- Conducting simulated external attack testing of AI endpoints. For example, performing automated attack simulations, testing endpoint protection effectiveness against high-volume and distributed attacks, and documenting methodologies appropriate to organizational threat profile.
- Maintaining endpoint security through remediation. For example, tracking identified vulnerabilities, implementing protective measures based on testing outcomes, and regularly updating endpoint defenses and detection thresholds.
---

## B005: Implement real-time input filtering

### Control shoulds
- Integrating automated moderation tools to filter inputs before they reach the foundation model. For example, integrating third-party moderation APIs, implementing custom filtering rules, configuring blocking or warning actions for flagged content, and establishing confidence thresholds based on risk category and severity

### Control mays
- Documenting the moderation logic and rationale. For example, explaining chosen moderation tools, threshold justifications, and decision criteria for different risk categories.
- Providing feedback to users when inputs are blocked.
- Logging flagged prompts for analysis and refinement of filters, while ensuring compliance with privacy obligations.
- Periodically evaluating filter performance and adjusting thresholds accordingly. For example, accuracy, latency, false positives/negatives.
---

## B006: Prevent unauthorized AI agent actions

### Control shoulds
- Implementing technical restrictions that limit agent capabilities to authorized scope. For example, restricting agent access to approved backend services and APIs, enforcing network segmentation or API gateway rules, or implementing service-level authorization preventing access to sensitive systems.
- Deploying monitoring and alerting for agent actions that exceed security boundaries. For example, logging all agent service interactions, alerting on access attempts to unauthorized systems or APIs, or anomaly detection flagging unusual connection patterns.
---

## B007: Enforce user access privileges to AI systems

### Control shoulds
- Implementing system-level access controls tailored to AI systems. For example, using role-based or attribute-based access to restrict access to model configuration, training datasets, tool-calling capabilities, or prompt logs, based on job function and system sensitivity.
- Restricting administrative and configuration privileges to authorized personnel. For example, limiting ability to alter system behavior, tools, or models.
- Conducting access reviews and updates at least quarterly. For example, validating access assignments, updating based on policy or role changes, documenting access changes with AI-specific context (e.g. model access justification, changes to agent capability boundaries, or access to sensitive prompt/response history).
---

## B008: Protect model deployment environment

### Control shoulds
- Implementing model access protection. For example, restricting access to production AI models based on job function and operational need, implementing MFA for model system access, maintaining user access reviews appropriate to organizational size.
- Establishing deployment security controls. For example, applying scoped API tokens or signed requests, using TLS for all endpoint traffic, implementing schema validation to protect model APIs from malformed or adversarial input.

### Control mays
- Securing model hosting environments. For example, using up-to-date and minimal container images, scanning for known vulnerabilities in dependencies and base images, and applying infrastructure-level isolation techniques based on risk level (e.g. container namespaces, VM separation, or dedicated GPU access).
- Verifying model integrity before and during deployment. For example, using cryptographic checksums or signed artifacts to detect tampering, scanning model files for malicious payloads.
---

## B009: Limit output over-exposure

### Control shoulds
- Reducing or limiting the number of results shown in outputs to relevant only to balance security and utility. For example, character limits, limits on inference time.

### Control mays
- Providing user-facing notices or documentation about output limitations.
- Limiting the fidelity of model outputs in certain use cases. For example, applying output rounding, threshold bands, or obfuscation techniques to reduce the risk of model inversion.
---

## C001: Define AI risk taxonomy

### Control shoulds
- Defining risk categories with severity levels and examples based on industry and deployment context. For example, classifying harmful outputs such as distressed outputs, angry responses, high-risk advice, offensive content, bias, and deception, identifying other high-risk use cases such as safety-critical instructions, legal recommendations, financial advice.
- Aligning risk taxonomy with external frameworks and standards.
- Establishing severity grading appropriate to organizational context and risk tolerance. For example, implementing consistent scoring methodology across risk categories, defining thresholds for flagging and human review.
- Maintaining taxonomy currency with documented change management. For example, updating based on emerging threats or incidents.
---

## C002: Conduct pre-deployment testing

### Control shoulds
- Conducting pre-deployment testing with documented results and identified issues. For example, structured hallucination testing, adversarial prompting, safety unit tests, and scenario-based walkthroughs.
- Completing risk assessments of identified issues before system deployment. For example, potential impact analysis, mitigation strategies, and residual risk evaluation.
- Obtaining approval sign-offs from designated accountable. For example, documented rationale for approval decisions and maintained records for review purposes.

### Control mays
- Integrating AI system testing into established software development lifecycle (SDLC) gates. For example, including threat modelling and risk evaluation during design phases, requiring risk evaluation and sign-off at staging or pre-production milestones, aligning with CI/CD or MLOps pipelines, and documenting test artefacts in shared repositories."
- Implementing pre-deployment vulnerability scanning of AI artifacts and dependencies. For example, scanning AI models and ML libraries for security vulnerabilities, validating runtime behavior for unsafe operations, and analyzing outputs for harmful content before deployment.
---

## C003: Prevent harmful outputs

### Control shoulds
- Implementing content filtering for harmful output types. For example, detecting and blocking distressed responses, angry language, offensive content, biased statements, and deceptive information.
- Implementing guardrails for advice generation. For example, restricting high-risk recommendations in sensitive domains, requiring disclaimers for guidance.

### Control mays
- Implementing bias detection and mitigation controls. For example, monitoring for discriminatory patterns, implementing fairness checks in outputs.
- Evaluating harm mitigation controls using performance metrics.
---

## C004: Prevent out-of-scope outputs

### Control shoulds
- Detecting and blocking out-of-scope requests. For example, detecting conversations outside intended use cases, blocking prohibited topics, providing redirection messages when users hit boundaries, and escalating or restricting access for repeated violations.
- Tracking out-of-scope violations and updating boundaries. For example, logging boundary violations, adjusting restrictions based on misuse patterns.

### Control mays
- Providing user guidance on system capabilities and limitations. For example, communicating what the AI system can and cannot do, intended use cases, and topics or requests outside the system's scope.
---

## C005: Prevent customer-defined high risk outputs

### Control shoulds
- Implementing detection and blocking mechanisms aligned with organizational risk taxonomy. For example, deploying filtering based on defined risk categories and severity thresholds.
- Implementing response actions for detected risks. For example, blocking high-severity outputs, flagging medium-risk content for review, logging violations for monitoring and analysis.

### Control mays
- Establishing escalation procedures for flagged high-risk content. For example, defining when human review is required and establishing approval workflows for edge cases.
- Implementing automated real-time interventions. For example, blocking or modifying outputs based on severity.
---

## C006: Prevent output vulnerabilities

### Control shoulds
- Establishing output sanitization and validation procedures before presenting content to users. For example, encoding or stripping potentially malicious content, validating structured outputs against safe schemas, blocking unsafe URLs, and enforcing secure rendering modes.
- Implementing security labeling and content handling based on trust level. For example, marking untrusted or third-party content, distinguishing external data from system-generated content, and applying differentiated security controls based on content source.

### Control mays
- Detecting advanced output-based attack patterns. For example, identifying prompt injection attempts, model subversion techniques, payloads targeting downstream systems, or obfuscated exploits designed to bypass filters.
---

## C007: Flag high risk outputs

### Control shoulds
- Defining high-risk output criteria drawing on risk taxonomy.
- Implementing automated detection mechanisms for high-risk outputs. For example, using content filtering, risk scoring, or classification models to identify outputs requiring review or flagging.

### Control mays
- Establishing human review workflows for flagged high-risk outputs. For example, assigning reviewers, defining escalation procedures for complex cases, managing review queues with response time tracking, and documenting review decisions.
---

## C008: Monitor AI risk categories

### Control shoulds
- Establishing ongoing monitoring of AI outputs across risk categories. For example, conducting regular evaluations prioritized by risk severity, sampling outputs for review, and tracking system behavior patterns.

### Control mays
- Maintaining documentation. For example, recording identified scenarios with clear examples, updating risk taxonomy based on monitoring findings and incidents.
- Integrating AI output monitoring with existing security tools. For example, forwarding alerts and flagged outputs to SIEM platforms, applying standard logging formats (e.g. JSON, syslog) to support automated threat detection workflows.
---

## C009: Enable real-time feedback and intervention

### Control shoulds
- Enabling user intervention capabilities. For example, providing mechanisms for users to pause, stop, or redirect system behavior, implementing feedback collection tools for users to report issues or concerns, ensuring technical controls persist across devices and interaction contexts.
- Ensuring accessibility of feedback and intervention mechanisms. For example, adhering to WCAG 2.1 standards for color contrast, screen reader compatibility, keyboard navigation, and clear messaging for users with disabilities.

### Control mays
- Reviewing user feedback and intervention logs regularly. For example, evaluating patterns in interventions, adapting communication methods based on user needs and emerging risk considerations.
- Analyzing collected feedback using structured methodologies. For example, categorizing by risk domain, prioritizing based on frequency and severity, routing high-impact or repeat issues into product backlog or compliance workflows.
---

## C010: Third-party testing for harmful outputs

### Control shoulds
- Appointing qualified third-party assessors. Including selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. Including performing assessments of harmful outputs at least every quarter, defining testing scope and methodologies based on risk classifications and industry benchmarks like ToxiGen, coordinating with internal security and testing teams.
- Maintaining documentation. Including testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## C011: Third-party testing for out-of-scope outputs

### Control shoulds
- Appointing qualified third-party assessors. Including selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. Including defining testing scope and methodologies based on risk taxonomy and performing assessments of out-of-scope outputs at least every quarter. 
- Maintaining documentation. Including testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## C012: Third-party testing for customer-defined risk

### Control shoulds
- Appointing qualified third-party assessors. Including selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. Including defining testing scope and methodologies based on risk taxonomy and performing assessments of high-risk areas at least every quarter.
- Maintaining documentation. Including testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## D001: Prevent hallucinated outputs

### Control shoulds
- Implementing factual accuracy controls. For example, deploying available fact-checking mechanisms, flagging uncertain or low-confidence responses.
- Establishing information source validation. For example, requiring citations for factual claims, implementing source reliability checks.

### Control mays
- Maintaining uncertainty communication. For example, displaying confidence levels, providing appropriate disclaimers for generated information.
---

## D002: Third-party testing for hallucinations

### Control shoulds
- Appointing qualified third-party assessors. Including selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. Including defining testing scope and methodologies based on risk taxonomy and performing assessments at least every quarter.
- Maintaining documentation. Including testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## D003: Restrict unsafe tool calls

### Control shoulds
- Implementing function call validation and authorization. For example, restricting tool access to approved functions, validating parameters before execution.
- Enforcing rate limits and transaction caps for autonomous tool use.
- Establishing execution monitoring and logging. For example, tracking all tool calls, monitoring for unauthorized access attempts or scope violations.

### Control mays
- Requiring human approval for sensitive tool operations. For example, requiring human confirmation before executing high-risk actions, implementing approval workflows for operations beyond autonomous boundaries.
- Reviewing patterns of AI tool usage. For example, identifying anomalies, updating tool permissions, and retiring unused or high-risk functions during scheduled evaluations.
---

## D004: Third-party testing of tool calls

### Control shoulds
- Appointing qualified third-party assessors. Including selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. Including defining testing scope and methodologies based on risk taxonomy and performing assessments of tool calls at least every quarter.
- Maintaining documentation. Including testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## E001: AI failure plan for security breaches

### Control shoulds
- Assigning a breach response lead from existing staff. For example, IT manager, security officer, or designated executive with authority to engage external counsel and specialists as needed.
- Defining breach notification procedures. For example, customer communications, regulatory reporting requirements, and vendor notifications based on applicable privacy laws.
- Implementing security remediation measures. For example, system freeze capabilities, vulnerability fixes, access control updates, and coordination with external security consultants when internal expertise is insufficient.
- Establishing evidence collection requirements with guidance on preserving evidence for potential legal review. For example, system logs, user activity records, and basic documentation.
---

## E002: AI failure plan for harmful outputs

### Control shoulds
- Implementing customer communication protocols. For example, disclosure procedures, explanation of corrective actions, and follow-up commitments with executive approval for significant incidents.
- Establishing immediate mitigation steps with designated staff responsibilities. For example, system freeze capabilities, output suppression, customer notification, and system adjustments.

### Control mays
- Defining harmful output categories with reference to risk taxonomy. For example, discriminatory content, offensive material, inappropriate recommendations, ideally with concrete examples.
- Coordinating external support engagement. For example, legal counsel consultation, PR support, and insurance claim procedures.
---

## E003: AI failure plan for hallucinations

### Control shoulds
- Establishing compensation assessment procedures. For example, loss evaluation methods, settlement approaches, and payment authorization levels with appropriate approval requirements.
- Implementing remediation measures. For example, system freeze capabilities, model adjustments, output validation improvements, customer notification, and enhanced monitoring.

### Control mays
- Defining hallucination incident types. 
- Coordinating potential external support. For example, legal consultation for significant claims, financial review when needed, and insurance coverage activation.
---

## E004: Assign accountability

### Control shoulds
- Defining AI system changes requiring approval including model selection, material changes to the meta prompt, adding / removing guardrails, changes to end-user workflow, other changes that drive material. For example, +/-10% performance on evals.
- Assigning an accountable lead as approver for each of these changes. Can follow a RACI structure to formalize roles of those consulted and informed.

### Control mays
- Implementing code signing and verification processes for AI models, libraries, and deployment artefacts to ensure only digitally signed components are approved for production use.
---

## E005: Assess cloud vs on-prem processing

### Control shoulds
- Conducting deployment risk assessments. For example, evaluating data sensitivity, regulatory compliance requirements, IP protection needs, and security controls for cloud vs. on-premises AI processing.
- Documenting decision criteria and rationale. For example, establishing clear selection factors, maintaining records of deployment choices with business justification.
- Reviewing deployment decisions when requirements change. For example, reassessing choices when data sensitivity, regulations, or threat landscape evolves.
---

## E006: Conduct vendor due diligence

### Control shoulds
- Defining assessment criteria for foundational or upstream AI models. For example, data handling and ownership practices, PII controls, security measures, compliance status, open-source.
- Conducting documented assessments. For example, scoring results, verification activities such as certifications reviewed and references contacted, and approval decisions. 
- Maintaining assessment records with sufficient detail for audit purposes and retaining due diligence evidence before vendor approval.
---

## E007: [Retired] Document system change approvals

### Control shoulds
- Documenting formal review and approval decisions for changes defined in E004: Assign accountability.
---

## E008: Review internal processes

### Control shoulds
- Reviewing decision processes every quarter including AI system changes, foundational model selection, security assessment.
- Maintaining a centralized repository of decision records and internal review of these record. For example, supporting evidence reviewed, remediation plans.
- Documenting and tracking remediation of any risks identified.int

### Control mays
- Collecting and implementing external feedback on AI systems. For example, system risks, new threat patterns, new mitigation strategies.
---

## E009: Monitor third-party access

### Control shoulds
- Configuring logging for third-party interactions. For example, capturing API connections, user access sessions, data exchanges, and service integrations.
- Capturing access metadata. For example, user identification, authentication timestamps, accessed resources, session duration, origin IP addresses, and resource usage patterns.
---

## E010: Establish AI acceptable use policy

### Control shoulds
- Defining prohibited AI usage for end-users. For example, jailbreak attempts, malicious prompt injection, unauthorized data extraction, generation of harmful content, and misuse of customer data.
- Implementing detection and monitoring tools. For example, prompt analysis, output filtering, usage pattern anomalies, and suspicious access attempts.
- Implementing user feedback when policy is breached. For example, showing alerts or error messages when inputs violate acceptable use.

### Control mays
- Real-time monitoring, blocking, or alerting capabilities.
- Maintaining logging and tracking systems. For example, incident creation, violation tracking with case assignment and resolution documentation.
- Conducting regular effectiveness reviews. For example, quarterly analysis of violation trends, tool performance assessment, policy updates based on emerging threats, and user training adjustments.
---

## E011: Record processing locations

### Control shoulds
- Maintaining AI infrastructure location documentation. For example, geographic locations of foundation model processing locations and inference endpoint regions, documenting third-party AI service provider data handling locations.
- Reviewing and updating documentation regularly.

### Control mays
- Implementing transfer compliance procedures. For example, assessing data transfer requirements for AI training data and inference processing, maintaining approved transfer mechanisms for foundation model providers and AI infrastructure, mitigating transfer risk for cross-border AI model training.
---

## E012: Document regulatory compliance

### Control shoulds
- Identifying relevant regulations. For example, data protection laws. For example, GDPR, CCPA, sector-specific requirements, emerging AI standards. For example, EU AI Act.
- Documenting compliance procedures and strategies appropriate for company size and operations.
- Reviewing the repository every 6 months and when additional requirements may be triggered. For example, regulations change or business operations expand into new jurisdictions.
---

## E013: Implement quality management system

### Control shoulds
- Defining quality objectives, metrics, and risk management approach for AI systems. For example, establishing performance targets, safety thresholds, risk assessment methodologies, and measurement processes appropriate to system risk level.
- Establishing change management, approval processes, and documentation standards. For example, defining review and approval requirements for AI system changes, assigning accountability for quality decisions, documenting design and development procedures.
- Implementing defect tracking, continuous improvement, and post-market monitoring. For example, maintaining issue tracking systems, conducting root cause analysis, documenting corrective actions, establishing post-market monitoring processes.

### Control mays
- Establishing data management and record-keeping systems. For example, documenting data governance procedures, maintaining technical documentation, implementing record retention policies for model training data and system outputs.
- Documenting communication procedures with regulatory authorities and stakeholders. For example, establishing protocols for regulatory reporting, stakeholder notifications for incidents, and procedures for authority interactions.
---

## E014: Share transparency reports

### Control mays
This requirement was merged into E017 at the Q1, 2026 standard update. See aiuc-1.com/changelog for more information
---

## E015: Log model activity

### Control shoulds
- Capturing system activity details to support incident investigation and behavior explanation. For example, logging inputs, processing steps, outputs, and metadata for AI systems.
- Implementing log storage with appropriate retention periods, access controls, and data sanitation to support auditing and incident response.

### Control mays
- Implementing technical controls to ensure logs are tamper-evident and independently verifiable. For example, ensuring that captured records cannot be modified or deleted after creation, ensuring sequence integrity so that gaps, omissions, and reordering are detectable during incident investigation or audit.
---

## E016: Implement AI disclosure mechanisms

### Control shoulds
- Implementing AI disclosure for text-based interactions. For example, displaying clear notices when users interact with AI chatbots, virtual assistants, or automated messaging systems.
- Implementing AI disclosure for voice-based interactions. For example, providing audio notifications at the beginning of voice calls or interactions.
- Labelling AI-generated media and documents in a machine-readable and detectable format. For example, marking AI-generated images, videos, audio, or documents with metadata, watermarks, or labels indicating artificial generation.
- Disclosing when autonomous AI agents or automated workflows are performing actions. For example, notifying users when AI systems are making decisions, processing requests, or executing tasks without human oversight.
- Establishing reactive disclosure capabilities when users ask if they are interacting with AI.
---

## E017: Document system transparency policy

### Control shoulds
- Establishing a transparency policy defining documentation requirements for major AI systems. For example, specifying required documentation elements, establishing documentation standards.
- Creating transparency documentation for major AI systems. For example, documenting system characteristics, data provenance, and model behavior for systems meeting documentation criteria.

### Control mays
- Defining policies for sharing transparency documentation with external stakeholders. For example, establishing when reports are shared, specifying recipient categories, determining what information is disclosed to each stakeholder type.
- Documenting sharing procedures including approval workflows, version control, and distribution tracking. For example, establishing approval requirements before external sharing, maintaining version control of shared documents, tracking which stakeholders received which versions.
---

## F001: Prevent AI cyber misuse

### Control shoulds
- Results of testing from foundation model developer on offensive cyber capabilities and mitigations.

### Control mays
- Implementing malicious use detection and blocking. For example, deploying available content filtering to detect requests for malicious code generation, attack planning, and vulnerability exploitation guidance, configuring automated blocking of cyber attack assistance requests, maintaining databases of prohibited use patterns.
---

## F002: Prevent catastrophic misuse

### Control shoulds
- Results of testing from foundation model developer on CBRN capabilities and mitigations.

### Control mays
- Establishing catastrophic misuse monitoring. For example, monitoring AI system interactions for patterns indicating weapons development or mass harm intent, implementing real-time alerting for detected catastrophic misuse attempts, documenting suspicious queries and system responses.
---

