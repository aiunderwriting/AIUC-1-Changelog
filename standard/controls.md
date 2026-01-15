# Controls

## A001: Establish input data policy

### Control shoulds
- Defining input data usage policies. For example, opt-in/opt-out mechanisms, disclosure requirements, boundaries between training and post-deployment data usage.
- Implementing data retention and deletion procedures for inputs. For example, defining retention periods for training data, inference logs, and customer-submitted content, plus technical approaches for removal such as selective unlearning.
- Documenting and justifying retention periods for different categories of input data.

### Control mays
- Documenting processes for customer data subject rights. For example, handling requests for access, portability, or deletion of input data, and maintaining records of which datasets were used to train specific models.
---

## A002: Establish output data policy

### Control shoulds
- Defining output ownership rights with clear distinctions between customer inputs and AI outputs. For example, specifying customer versus vendor ownership of AI-generated content, usage permissions for different output types.
- Disclosing consent and opt-out procedures for outputs. For example, documenting how consent for re-use of AI-generated content is collected, what opt-out limitations exist, and how customers can control or revoke permissions.
- Establishing output usage policies communicated through accessible terms of service. For example, permitted uses of AI-generated content, restrictions on redistribution or commercial use, policies on derivative and transformative use.
---

## A003: Limit AI agent data collection

### Control shoulds
- Configuring data collection limits to reduce data and privacy exposure. For example, limiting to time-bounded, task-specific, purpose-limited contextual data, implementing scoping actions based on agent-assigned objectives, session type, or workflow stage, and avoiding persistent or out-of-scope information requests.

### Control mays
- Deploying monitoring and enforcement mechanisms. For example, ensuring AI systems only perform necessary inference and logging deviations from defined operational scope.
- Integrating with existing identity and access management (IAM) systems to align agent access permissions with organizational policies. For example, oAuth.
- Establishing dynamic context-based restrictions to adjust access decisions if user role or environment changes during agent session. For example, task-based access controls, contextual capability restrictions, automatic privilege limiting.
---

## A004: Protect IP & trade secrets

### Control shoulds
- Documenting foundation model provider safeguards which may serve as primary IP protection. For example, reviewing contractual data handling terms, assessing model retention and fine-tuning behaviors, verifying confidentiality commitments, and identifying any limitations or gaps against organizational IP protection criteria.
- Establishing supplementary data access controls where provider protections are insufficient. For example, limiting AI exposure to proprietary information, restricting training on internal documents, and applying differentiated controls for open-source versus proprietary assets.

### Control mays
- Implementing output monitoring procedures with automated review processes for high-risk scenarios. For example, scanning responses for proprietary code or business information, flagging internal data disclosures.
- Maintaining internal IP incident response and escalation procedures as part of AI failure plan on data breaches. For example, documenting incidents and containment actions, specifying clear escalation timelines and responsible parties based on severity. 
---

## A005: Prevent cross-customer data exposure

### Control shoulds
- Establishing explicit consent and disclosure for combined data usage. For example, informing customers when their data will be combined with competitor data, disclosing data anonymization and abstraction policies, providing opt-out mechanisms.
- Implementing customer data isolation controls. For example, enforcing strict logical and physical separation of customer data, applying tenant-specific encryption, validating data flow boundaries in shared infrastructure, establishing technical barriers between customer datasets during training.

### Control mays
- Implementing specific privacy-enhancing technologies (PETs) to reduce competitive exposure. For example, applying differential privacy to obfuscate customer contributions, using federated learning to avoid centralizing raw data.
- Implementing inference-time data isolation to prevent leakage of one customer's data or model-derived insights into responses for other customers. For example, enforcing tenant-aware routing, access control at inference, and prompt context segregation.
- Adapting safeguards to industry-specific competitive risks. For example, applying stricter isolation for customers in the same vertical, avoiding cross-training on data from direct competitors, or honoring industry codes of conduct and regulatory expectations around data co-mingling.
---

## A006: Prevent PII leakage

### Control shoulds
- Establishing data segregation controls. For example, isolating user sessions, implementing user-specific boundaries, preventing reuse of prompts or outputs containing personal identifiers, maintaining dataset isolation.
- Establishing safeguards to prevent personal data leakage between users. For example, isolating user sessions, applying user-specific output boundaries, and preventing reuse of prompts or outputs containing personal identifiers.
- Documenting protection procedures and incident management. For example, identifying PII, defining output handling policies, maintaining leakage incident records and remediation actions.

### Control mays
- Implementing output monitoring. For example, scanning outputs for cross-customer data leakage, validating data source attribution.
- Implementing automated detection and redaction of personal data in AI outputs. For example, using named entity recognition (NER) or data classification tools to scan and remove PII before output is delivered to end users.
- Integrating with existing data loss prevention (DLP) systems to monitor and block outputs containing personal data in violation of policy.
---

## A007: Prevent IP violations

### Control shoulds
- Documenting foundation model provider IP protections which may serve as primary infringement safeguards. For example, reviewing copyright and trademark handling, assessing indemnification coverage, and identifying known limitations, exclusions, or risk thresholds relevant to organizational context.
- Establishing supplementary content filtering mechanisms where provider protections have gaps or limitations. For example, detecting copyrighted material in outputs, implementing trademark screening.

### Control mays
- Implementing user guidance and guardrails to reduce IP risk. For example, providing usage policies that explain prohibited content types, embedding warnings or UI notices for high-risk prompts, restricting output generation in known infringement domains. 
- Maintaining third-party IP incident response procedures. For example, identifying potential infringement, documenting incidents and remediation actions, coordinating with provider protections.
- Implementing restrictions in AI acceptable use policy.
---

## B001: Third-party testing of adversarial robustness

### Control shoulds
- Establishing a taxonomy for adversarial risks. For example, referencing and tailoring relevant categories from NIST's AI 100-2e2023 attack classifications (chapters 2.1 and 3.1) such as evasion, poisoning, privacy attacks, and model manipulation, and aligning these to system architecture and use cases.
- Conducting comprehensive adversarial testing quarterly and after material system changes. For example, performing structured red-teaming, prompt injection assessments, jailbreaking attempts, adversarial perturbation testing, semantic manipulation, and simulated malicious tool invocations using defined attack trees or scenario templates.
- Maintaining secure testing documentation. For example, recording test cases, methods, outcomes, and system behaviors with restricted access controls, implementing secure storage for sensitive testing materials.
- Establishing improvement processes based on findings. For example, assigning owners and remediation timelines based on test severity (e.g. critical within 30 days), tracking fixes through risk registers or issue management systems, documenting updates to safeguards and procedures.

### Control mays
- Aligning adversarial testing with broader security testing programs. For example, integrating AI-specific test cases into penetration testing, sharing threat models across red/blue teams, aligning test cycles with security audit and compliance calendars.
---

## B002: Detect adversarial input

### Control shoulds
- Establishing detection and alerting. For example, implementing monitoring for prompt injection patterns, jailbreak techniques, adversarial input attempts, and exceeding rate limits, configuring alerts and threat notifications for suspicious activities.
- Implementing incident logging and response procedures. For example, logging suspected attacks with timestamps, user/session context, and input content, escalating to designated personnel based on severity thresholds (e.g. immediate escalation for confirmed jailbreaks), documenting response actions in a centralized incident system.
- Maintaining detection effectiveness through quarterly reviews. For example, updating detection rules based on emerging adversarial techniques, analyzing incident patterns and documenting system improvements.

### Control mays
- Implementing adversarial input detection prior to AI model processing where feasible. For example, using lightweight pattern-matching, behavioral heuristics, or IP-based filters to flag likely threats before processing, with latency-optimized safeguards or asynchronous review paths where real-time detection is infeasible.
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
- Implementing systems distinguishing between high-volume legitimate usage and adversarial behavior. For example, using behavioral analytics, session history, user role, and customer tier to calibrate thresholds and prevent false positives against known trusted users.
- Implementing rate limiting and query restrictions. For example, establishing per-user query quotas and rate limits to prevent model extraction attempts, configuring automated blocking of excessive query patterns, implementing progressive restrictions for suspicious usage behavior, implementing pseudo limits such as significant price-per-query increases over a set quota.
- Conducting simulated external attack testing. For example, performing automated scraping tests, brute force attempts, and reconnaissance activities against AI endpoints, testing rate limiting effectiveness against high-volume query attacks and distributed attacks, documenting test methodologies and scope appropriate to organizational threat profile.
- Maintaining endpoint security through remediation. For example, documenting test results and identified vulnerabilities, implementing protective measures and updating endpoint defenses based on testing outcomes, regularly reviewing and adjusting rate limiting thresholds based on attack patterns.
---

## B005: Implement real-time input filtering

### Control shoulds
- Integrating automated moderation tools to scan user inputs for violations of content policies such as violence, hate, or self-harm. For example, integrating OpenAI’s Moderation API, configuring Claude for content moderation, implementing moderation tools from e.g. VirtueAI/Hive/Spectrum Labs, developing custom filters, or a combination.
- Blocking, redirecting, or modifying flagged inputs before they reach the foundation model.
- Establishing confidence thresholds or rules for when to block, warn, log, or allow inputs based on risk category and severity.
- Documenting the moderation logic and thresholds used, including rationale for chosen tool(s).

### Control mays
- Providing feedback to users when inputs are blocked.
- Logging flagged prompts for analysis and refinement of filters, while ensuring compliance with privacy obligations. For example, excluding identifying metadata, applying retention limits, and documenting user-facing disclosures or consent mechanisms if required.
- Periodically evaluating filter performance and adjusting thresholds accordingly. For example, accuracy, latency, false positives/negatives.
---

## B006: Limit AI agent system access

### Control shoulds
- Configuring contextual access controls for AI agents. For example, enforcing task-based tool access using declarative policy models (e.g. JSON policy schemas or role-capability matrices), scoping actions based on agent-assigned objectives, session type, or workflow stage.
- Implementing privilege limiting for autonomous behavior. For example, restricting agents from escalating access or acting beyond permitted functions.
- Deploying monitoring and enforcement mechanisms. For example, ensuring AI systems only perform necessary inference and logging deviations from defined operational scope.

### Control mays
- Defining automatic restriction triggers. For example, revoking tool access or suppressing outputs when agent context diverges from declared task scope, user role constraints are violated, or anomalous behavior (e.g. lateral tool access or excessive data usage) is detected in real time.
- Integrating agent access decisions with existing identity and access management (IAM) systems. For example, aligning agent privileges with user roles, enforcing access through API gateways or policy engines, and logging agent actions alongside traditional user activity.
---

## B007: Enforce user access privileges to AI systems

### Control shoulds
- Implementing system-level access controls tailored to AI systems. For example, using role-based or attribute-based access to restrict access to model configuration, training datasets, tool-calling capabilities, or prompt logs, based on job function and system sensitivity.
- Restricting administrative and configuration privileges to authorized personnel. For example, limiting ability to alter system behavior, tools, or models.
- Conducting access reviews and updates at least quarterly. For example, validating access assignments, updating based on policy or role changes,  documenting access changes with AI-specific context (e.g. model access justification, changes to agent capability boundaries, or access to sensitive prompt/response history).
---

## B008: Protect model deployment environment

### Control shoulds
- Implementing model access protection. For example, restricting access to production AI models based on job function and operational need, implementing MFA for model system access, maintaining user access reviews appropriate to organizational size.
- Establishing deployment security controls. For example, applying scoped API tokens or signed requests, using TLS for all endpoint traffic, implementing schema validation to protect model APIs from malformed or adversarial input.

### Control mays
- Securing model hosting environments. For example, using up-to-date and minimal container images, scanning for known vulnerabilities in dependencies and base images, and applying infrastructure-level isolation techniques based on risk level (e.g. container namespaces, VM separation, or dedicated GPU access).
- Verifying model integrity before and during deployment. For example, using cryptographic checksums or signed artifacts to detect tampering, scanning model files for malicious payloads (e.g. in Pickle or ONNX formats), and logging model version hashes at deployment time.
---

## B009: Limit output over-exposure

### Control shoulds
- Reducing or limiting the number of results shown in outputs to relevant only to balance security and utility. For example, character limits, limits on inference time.
- Filtering sensitive information that may reveal internal system behavior. For example, removing or abstracting technical details about model architecture, prompt structure, or tool invocation logic.
- Providing user-facing notices or documentation about output limitations. For example, clearly indicating when results have been truncated, rounded, or suppressed to align with security and privacy safeguards.

### Control mays
- Limiting the fidelity of numerical outputs in certain use cases. For example, applying output rounding, threshold bands, or obfuscation techniques to reduce the risk of model inversion or precision-sensitive data disclosure.
---

## C001: Define AI risk taxonomy

### Control shoulds
- Defining risk categories with severity levels and examples based on industry and deployment context. For example, classifying harmful outputs such as distressed outputs, angry responses, high-risk advice, offensive content, bias, and deception, identifying other high-risk use cases such as safety-critical instructions, legal recommendations, financial advice.
- Aligning risk taxonomy with external frameworks and standards. For example, NIST AI RMF functions, EU AI Act article 9, ISO42001 controls. 
- Establishing severity grading appropriate to organizational context and risk tolerance. For example, implementing consistent scoring methodology across risk categories, defining thresholds for flagging and human review.
- Maintaining taxonomy currency with documented change management. For example, reviewing and updating risk categories quarterly or when new threat patterns emerge, adjusting risk thresholds, incorporating lessons from incident response and industry benchmarks.

### Control mays
- Identifying additional risk categories that are considered harmful given nature of operations. For example, hallucinations, out-of-scope content.
---

## C002: Conduct pre-deployment testing

### Control shoulds
- Conducting pre-deployment testing with documented results and identified issues. For example, structured hallucination testing, adversarial prompting, safety unit tests, and scenario-based walkthroughs.
- Completing risk assessments of identified issues before system deployment. For example, potential impact analysis, mitigation strategies, and residual risk evaluation.
- Obtaining approval sign-offs from designated accountable leads with documented rationale for approval decisions and maintained records for review purposes.

### Control mays
- Integrating AI system testing into established software development lifecycle (SDLC) gates. For example, requiring risk evaluation and sign-off at staging or pre-production milestones, aligning with CI/CD or MLOps pipelines, and documenting test artifacts in shared repositories.
- Implementing pre-deployment vulnerability scanning of AI artifacts and dependencies. For example, scanning model files (e.g. pickle, ONNX) for malicious code or unsafe deserialization, checking runtime behavior for unbounded tool execution or insecure API access, validating ML libraries and infrastructure for known CVEs, and analyzing downstream outputs for unsafe content or behaviors.
---

## C003: Prevent harmful outputs

### Control shoulds
- Implementing content filtering for harmful output types. For example, detecting and blocking distressed responses, angry language, offensive content, biased statements, and deceptive information.
- Establishing safety guardrails for advice generation. For example, restricting high-risk recommendations in sensitive domains, requiring disclaimers for guidance.
- Maintaining bias detection and mitigation controls. For example, monitoring for discriminatory patterns, implementing fairness checks in outputs.

### Control mays
- Evaluating harm mitigation controls using performance metrics. For example, tracking false positives (overblocking safe content) and false negatives (missed harmful content), measuring coverage of flagged scenarios, and benchmarking against known harm datasets like ToxiGen. 
- Establishing review and appeal mechanisms. For example, allowing flagged outputs to be escalated for manual review, recording override decisions with justification, incorporating feedback into harm detection refinement.
---

## C004: Prevent out-of-scope outputs

### Control shoulds
- Implementing topic boundary enforcement. For example, detecting and redirecting conversations outside intended use cases as defined in AI acceptable use policy, blocking prohibited discussion areas such as political topics or out-of-scope advice. 
- Establishing scope violation response procedures. For example, automated redirection messages, escalation for persistent attempts.
- Maintaining scope monitoring and adjustment capabilities. For example, tracking boundary violations, updating restrictions based on emerging issues.

### Control mays
- Implementing user education on system scope and limitations. For example, displaying onboarding tooltips, publishing usage guidelines or FAQs, embedding in-context hints to clarify intended capabilities, highlighting unsupported domains to reduce misuse.
---

## C005: Prevent customer-defined high risk outputs

### Control shoulds
- Implementing detection and blocking mechanisms aligned with organizational risk taxonomy. For example, deploying filtering based on defined risk categories and severity thresholds.
- Maintaining risk-based response controls. For example, flagging and blocking mechanisms, logging for monitoring purposes.

### Control mays
- Establishing escalation procedures for flagged high risk content. For example, human review workflows, approval requirements for edge cases, planning reviewer capacity based on expected flagging volume and response time objectives.
- Implementing automated real-time response mechanisms. For example, triggering dynamic warnings, blocking or modifying model responses based on severity thresholds, routing flagged interactions for further processing or audit without user delay.
---

## C006: Prevent output vulnerabilities

### Control shoulds
- Establishing output sanitization and validation procedures before presenting content to users. For example, stripping or encoding HTML, JavaScript, shell syntax, and iframe content, blocking or rewriting unsafe URLs, validating structured output schemas (e.g. JSON/YAML/XML) against whitelists, enforcing safe rendering modes (e.g. text-only, content-security-policy (CSP) headers).
- Implementing safety-specific labeling and handling protocols. For example, clearly marking untrusted, distinguishing untrusted third-party data, applying appropriate security controls based on content source and risk level.
- Maintaining detection and monitoring capabilities. For example, logging sanitization activities, implementing alerting for suspicious content patterns.

### Control mays
- Detecting advanced output-based attack patterns. For example, identifying prompt injection chains, model-output subversion (e.g. jailbreak tokens), payloads targeting downstream applications (e.g. command-line instructions, SQL queries), or obfuscated exploits designed to bypass basic filters.
---

## C007: Flag high risk recommendations

### Control shoulds
- Defining high-risk recommendation criteria drawing on risk taxonomy. For example, financial advice exceeding company thresholds, medical or health-related guidance, legal recommendations, safety-critical instructions, and content that could cause reputational harm.
- Implementing automated detection using keyword filtering, confidence scoring, or rule-based assessment with adjustable sensitivity settings.
- Establishing human review workflows. For example, designated reviewers from available staff, escalation procedures for complex cases, queue management for pending reviews with response time tracking against SLA, documentation of review decisions.
---

## C008: Monitor AI risk categories

### Control shoulds
- Implementing proactive detection. For example, defining potential scenarios based on risk taxonomy that could generate harmful outputs under normal or adversarial use, documenting risk scenarios to guide test planning and operational safeguards, deploying automated detection tools (e.g. classifiers, heuristics, anomaly detectors).
- Establishing ongoing monitoring. For example, conducting regular evaluations prioritized by risk severity, using methods such as output sampling, behavior tracing, and prompt-response logging.
- Maintaining documentation. For example, recording identified scenarios with clear examples, updating risk taxonomy based on monitoring findings and incidents.

### Control mays
- Integrating AI output monitoring with existing security tools. For example, forwarding alerts and flagged outputs to SIEM platforms, applying standard logging formats (e.g. JSON, syslog) to support automated threat detection workflows.
---

## C009: Enable real-time feedback and intervention

### Control shoulds
- Establishing on-screen communication systems. For example, implementing real-time display of system status, intervention notices, disclaimers, and risk alerts during interactions, ensuring messages are context-sensitive and clearly visible.
- Enabling user intervention capabilities. For example, providing mechanisms for users to pause, stop, or redirect system behavior, implementing feedback collection tools for users to report issues or concerns, ensuring technical controls persist across devices and interaction contexts.
- Ensuring accessibility of feedback and intervention mechanisms. For example, adhering to WCAG 2.1 standards for color contrast, screen reader compatibility, keyboard navigation, and clear messaging for users with disabilities.
- Reviewing user feedback and intervention logs regularly. For example, evaluating patterns in interventions, adapting communication methods based on user needs and emerging risk considerations.

### Control mays
- Analyzing collected feedback using structured methodologies. For example, categorizing by risk domain, prioritizing based on frequency and severity,  routing high-impact or repeat issues into product backlog or compliance workflows.
---

## C010: Third-party testing for harmful outputs

### Control shoulds
- Appointing qualified third-party assessors. For example, selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. For example, performing assessments of harmful outputs at least every quarter, defining testing scope and methodologies based on risk classifications and industry benchmarks like ToxiGen, coordinating with internal security and testing teams.
- Maintaining documentation. For example, recording third-party qualifications, testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## C011: Third-party testing for out-of-scope outputs

### Control shoulds
- Appointing qualified third-party assessors. For example, selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. For example, performing assessments of out-of-scope outputs at least every quarter, defining testing scope and methodologies based on risk taxonomy.
- Maintaining documentation. For example, recording third-party qualifications, testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## C012: Third-party testing for customer-defined risk

### Control shoulds
- Appointing qualified third-party assessors. For example, selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. For example, performing assessments of high-risk areas at least every quarter, defining testing scope and methodologies based on risk taxonomy.
- Maintaining documentation. For example, recording third-party qualifications, testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
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
- Appointing qualified third-party assessors. For example, selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. For example, performing assessments of hallucinated outputs at least every quarter, defining testing scope and methodologies based on risk classifications.
- Maintaining documentation. For example, recording third-party qualifications, testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
---

## D003: Restrict unsafe tool calls

### Control shoulds
- Implementing function call validation and authorization. For example, restricting tool access to approved functions, validating parameters before execution.
- Enforcing rate limits and transaction caps for autonomous tool use.
- Establishing execution monitoring and logging. For example, tracking all tool calls, monitoring for unauthorized access attempts or scope violations.
- Maintaining decision boundary enforcement. For example, limiting autonomous actions to defined parameters, requiring human approval for sensitive operations.
- Reviewing patterns of AI tool usage for anomalies, updating tool permissions, and retiring unused or high-risk functions during scheduled evaluations.
---

## D004: Third-party testing of tool calls

### Control shoulds
- Appointing qualified third-party assessors. For example, selecting assessors with relevant technical capabilities for identified risk areas, maintaining records of assessor qualifications and independence.
- Conducting regular testing. For example, performing assessments of tool calls at least every quarter, defining testing scope and methodologies based on risk classifications.
- Maintaining documentation. For example, recording third-party qualifications, testing scope, results, and remediation actions taken, tracking follow-up activities and resolution timelines.
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
- Coordinating external support engagement. For example,  legal counsel consultation, PR support, and insurance claim procedures.
---

## E003: AI failure plan for hallucinations

### Control shoulds
- Establishing compensation assessment procedures. For example, loss evaluation methods, settlement approaches, and payment authorization levels with appropriate approval requirements.
- Implementing remediation measures. For example, system freeze capabilities, model adjustments, output validation improvements, customer notification, and enhanced monitoring.

### Control mays
- Defining hallucination incident types. For example,  factual errors or incorrect recommendations relevant to company context and customer base.
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
- Implementing deployment-appropriate security controls. For example, configuring cloud-specific protections or on-premises security measures based on selected deployment model.

### Control mays
- Implementing hybrid deployment strategies. For example, using on-premises for sensitive data, cloud for less sensitive workloads, with secure data flow controls.
- Establishing cloud vendor management procedures. For example, conducting provider due diligence, implementing contractual protections for data sovereignty and IP.
- Reviewing deployment decisions when requirements change. For example, reassessing choices when data sensitivity, regulations, or threat landscape evolves.
---

## E006: Conduct vendor due diligence

### Control shoulds
- Defining assessment criteria for foundational or upstream AI models. For example, data handling practices, PII controls, security measures, compliance status, open-source.
- Conducting documented assessments. For example, scoring results, verification activities such as certifications reviewed and references contacted, and approval decisions. Can follow a RACI structure.
- Maintaining assessment records with sufficient detail for audit purposes and retaining due diligence evidence before vendor approval.
---

## E007: Document system change approvals

### Control shoulds
- Documenting formal review and approval decisions for changes defined in E004: Assign accountability. 
- Documenting the approval workflow with sufficient detail for review purposes. For example, who approved the change, what evidence was reviewed, timestamp of approval. 
---

## E008: Review internal processes

### Control shoulds
- Reviewing decision processes every quarter including AI system changes, foundational model selection, security assessment.
- Maintaining a centralized repository of decision records and internal review of these record. For example, supporting evidence reviewed, remediation plans.
- Documenting and tracking remediation of any risks identified.

### Control mays
- Collecting and implementing external feedback on AI systems. For example, system risks, new threat patterns, new mitigation strategies.
---

## E009: Monitor third-party access

### Control shoulds
- Defining third-party interaction scope with logging of access attempts and activities. For example, API connections, user access sessions, data exchanges, and service integrations.
- Capturing access metadata. For example, user identification, authentication timestamps, accessed resources, session duration, origin IP addresses, and resource usage patterns.
---

## E010: Establish AI acceptable use policy

### Control shoulds
- Defining prohibited AI usage. For example, jailbreak attempts, malicious prompt injection, unauthorized data extraction, generation of harmful content, and misuse of customer data ideally with specific examples.
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
- Documenting strategy for compliance with conformity assessment procedures.
- Documenting techniques, procedures and systematic actions to be used for the design, design control and design verification of the AI system.
- Documenting techniques, procedures and systematic actions to be used for the development, quality control and quality assurance of the AI system.
- Documenting the handling of communication with national competent authorities, other relevant authorities, including those providing or supporting the access to data, notified bodies, other operators, customers or other interested parties.
- Documenting resource management, including security-of-supply related measures.
- Assigning and documenting accountability in the organisation for each of the aspects in the quality management system.

### Control mays
- Collecting comprehensive documentation for EU AI Act Article 17 requirements for quality management systems. For example, strategy for regulatory compliance, examination, test and validation procedures, technical specifications and fulfillment, data management procedures, risk management, post-market monitoring, incident reporting, and record-keeping.
---

## E014: Share transparency reports

### Control shoulds
- Defining report scope and recipient categories with clear criteria for when reports must be shared. For example, regulators, customers, and other stakeholders.
- Excluding or sanitizing technical documentation and other sensitive information that could be used for adversarial attacks.

### Control mays
- Implementing secure delivery methods with appropriate authentication and access control. For example,  dataroom access, encrypted transmission, controlled access portals.
- Documenting sharing procedures including approval workflows, version control, and audit trails for transparency.
---

## E015: Log model activity

### Control shoulds
- Capturing system activity details. For example, input parameters, processing steps, model outputs, and user interactions.
- Implementing log storage with appropriate retention periods and access controls to support auditing and incident response.
---

## E016: Implement AI disclosure mechanisms

### Control shoulds
- Implementing clear AI interaction disclosure at the beginning of communications, notifying users they are interacting with artificial intelligence, not humans.
- Ensuring disclosures are conspicuous and easily understood. For example, using prominent placement and plain language appropriate for the communication medium.
- Maintaining disclosure visibility throughout extended interactions. For example, providing ongoing indication of AI involvement in conversations or sessions.
- Labelling AI generated audio, image and video in a machine-readable format and detectable as artificially generated or manipulated. For example, Content Credentials. 
- Informing users if they are exposed to emotion recognition or biometric categorisation systems.

### Control mays
- Implementing adaptive disclosure methods for different interaction types. For example, visual indicators for text, audio notifications for voice communications.
- Establishing reactive disclosure capabilities when users ask if they are interacting with AI.
---

## E017: Document system transparency policy

### Control shoulds
- Establishing a transparency policy defining requirements for documentation of major AI systems. For example, model capabilities, limitations, and intended use cases.
- Maintaining a centralized repository of system documentation with appropriate access controls for internal stakeholders. For example, model cards, datasheets, and interpretability reports.
- Implementing updates to documentation when systems are modified or new information becomes available about model performance or risks.
---

## F001: Prevent AI cyber misuse

### Control shoulds
- Results of testing from foundation model developer on offensive cyber capabilities and mitigations.
- Attestation the mitigations have not been removed.

### Control mays
- Implementing malicious use detection and blocking. For example, deploying available content filtering to detect requests for malicious code generation, attack planning, and vulnerability exploitation guidance, configuring automated blocking of cyber attack assistance requests, maintaining databases of prohibited use patterns.
- Establishing usage monitoring and threat intelligence. For example, monitoring AI system usage for exploitation attempts and suspicious patterns, maintaining updated threat intelligence on AI misuse techniques, implementing alerting for detected malicious use attempts.
---

## F002: Prevent catastrophic misuse

### Control shoulds
- Results of testing from foundation model developer on CBRN capabilities and mitigations.
- Attestation that the mitigations have not been removed.

### Control mays
- Relevant evaluations. For example, Center for AI Safety's Weapons of Mass Destruction proxy benchmark.
- Establishing catastrophic misuse monitoring. For example, monitoring AI system interactions for patterns indicating weapons development or mass harm intent, implementing real-time alerting for detected catastrophic misuse attempts, documenting suspicious queries and system responses.
---

