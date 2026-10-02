## Chapter 7: AI Incident Response, Audit, and Assurance — Practice Questions

**Q1.** A financial services company discovers that their AI-powered loan approval system has been denying applications from a protected demographic group at a rate 3x higher than other groups. The issue was identified through quarterly fairness monitoring. What should be the FIRST step in their incident response?

A) Immediately retrain the model on a balanced dataset to fix the bias
B) Contain the incident by temporarily disabling the AI system and reverting to manual review processes
C) Notify all affected applicants and offer to re-review their applications
D) Conduct a full root cause analysis to determine why the bias occurred

<details>
<summary>Answer</summary>

**Correct: B**

Per AI incident response workflow (contain → investigate → remediate → document → report), containment is ALWAYS first to prevent ongoing harm. This means stopping the discriminatory system immediately. Investigation and remediation come after containment.

**Why the others are wrong:**
- Retraining is part of remediation, which comes AFTER containment and investigation. Cannot fix what you haven't diagnosed.
- Notification is part of post-incident actions, done AFTER containment and investigation. Must stop harm before addressing past harm.
- Root cause analysis is the investigation phase, which comes AFTER containment. Cannot investigate while system continues causing harm.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An AI chatbot deployed in healthcare begins providing medically dangerous advice after a model update. The incident was detected when a user complaint escalated to the legal department. During root cause analysis, which of the following would NOT typically be investigated as a potential cause?

A) Model drift from production data differing from training data
B) Adversarial inputs designed to manipulate the model's outputs
C) The demographic composition of the development team
D) Deployment error where wrong model version was pushed to production

<details>
<summary>Answer</summary>

**Correct: C**

Root cause analysis for AI focuses on technical and process failures: data issues, model drift, adversarial input, deployment error, human oversight failure. Team demographics relate to bias prevention during development but are not a root cause of a specific incident involving dangerous medical advice after deployment.

**Why the others are wrong:**
- Model drift is a primary root cause category - production data distribution changes can cause unexpected behavior.
- Adversarial attacks are a key root cause category - malicious inputs designed to trigger harmful outputs.
- Deployment errors are a primary root cause category - wrong model versions, configuration errors, etc.

</details>

---

**Q3.** A company is planning their first third-party AI audit. The audit scope includes reviewing the company's facial recognition system for fairness across demographic groups, validating that governance policies are being followed in practice, and confirming compliance with the EU AI Act. Which THREE types of audits does this scope encompass?

A) Algorithmic audit, process audit, and conformity assessment
B) Model audit, data audit, and compliance audit
C) Technical audit, operational audit, and financial audit
D) Internal audit, external audit, and regulatory audit

<details>
<summary>Answer</summary>

**Correct: A**

The scope describes: (1) Algorithmic audit - testing fairness/accuracy of the facial recognition model, (2) Process audit - validating governance policy compliance, and (3) Third-party conformity assessment - confirming EU AI Act compliance. These are the three specific AI audit types per AIGP framework.

**Why the others are wrong:**
- While partially correct ('compliance audit'), 'model audit' and 'data audit' are not the standard AI audit terminology. The framework uses 'algorithmic audit' and 'process audit'.
- These are general business audit categories, not AI-specific. Financial audits are not relevant to AI system evaluation.
- These describe audit performers/context (who does it, why), not audit types (what is being audited). The question asks about audit scope types.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** An e-commerce company's AI recommendation engine experiences a privacy breach when customer purchase history is exposed through model inversion attacks. After containment and investigation, the company must complete post-incident actions. Which of the following is NOT a standard post-incident action for this scenario?

A) Retrain the model with differential privacy techniques to prevent future model inversion
B) Update the incident response policy to include model inversion attack procedures
C) Replace the entire AI system with a rule-based recommendation engine
D) Notify affected customers whose purchase data was exposed

<details>
<summary>Answer</summary>

**Correct: C**

Standard post-incident actions include: model retraining (with improvements), policy updates, and affected party notification. Completely replacing the AI system with a different technology is a business decision, not a standard incident response action. The goal is to remediate and improve, not necessarily abandon AI.

**Why the others are wrong:**
- Model retraining with security improvements (like differential privacy) is a core post-incident remediation action.
- Policy updates to address newly discovered attack vectors are a standard post-incident action.
- Affected party notification is required for privacy breaches under most privacy regulations (GDPR, CCPA, etc.).

</details>

---

**Q5.** A manufacturing company using computer vision for quality control receives a regulatory inquiry from OSHA after three workplace injuries. Investigators want to audit whether the AI system properly identified safety hazards. The company must preserve evidence for the audit. Which documentation would be MOST critical to preserve first?

A) Marketing materials showing the AI system's advertised capabilities
B) Model training logs, inference logs for the specific incidents, and model version metadata
C) Employment records of the data science team who built the system
D) Customer testimonials and case studies about system effectiveness

<details>
<summary>Answer</summary>

**Correct: B**

For AI audit evidence preservation in a safety incident, technical documentation is critical: (1) Training logs show what the model learned, (2) Inference logs show what the model predicted during the incidents, (3) Model version metadata proves which version was deployed. This directly answers whether the AI system failed to identify hazards.

**Why the others are wrong:**
- Marketing materials may be relevant for liability but don't prove what the model actually did during the incidents. Secondary evidence at best.
- Team employment records are irrelevant to technical audit of model performance. May matter for general corporate investigation but not AI-specific audit.
- Testimonials are not technical evidence of what happened during specific incidents. Regulatory audit requires objective technical proof.

</details>

---

**Q6.** A healthcare AI system begins misdiagnosing a rare disease at a significantly higher rate than baseline. The issue is detected through automated monitoring alerts that track per-condition accuracy metrics. This detection method represents which category of AI incident detection?

A) User complaints - patients reporting incorrect diagnoses
B) Monitoring alerts - automated system detecting performance degradation
C) Regulatory inquiry - health authority investigation
D) Media reports - news coverage of misdiagnoses

<details>
<summary>Answer</summary>

**Correct: B**

The scenario explicitly states 'automated monitoring alerts that track per-condition accuracy metrics' detected the issue. This is the monitoring alerts detection category - proactive detection via automated systems before external discovery.

**Why the others are wrong:**
- No user complaints are mentioned. The monitoring system detected the issue proactively, not reactively from patient reports.
- No regulatory inquiry is mentioned. The incident was detected internally through monitoring, not external investigation.
- No media reports are mentioned. Internal monitoring detected this before any external awareness.

</details>

---

**Q7.** A company conducts an algorithmic audit of their hiring AI and discovers 8% accuracy difference across demographic groups (marginally above their 5% threshold). A process audit reveals the model review committee hasn't met in 6 months despite policy requiring monthly meetings. A compliance audit confirms the system isn't properly documented per EU AI Act requirements. Which finding represents the HIGHEST immediate risk requiring urgent remediation?

A) The 8% fairness gap in the algorithmic audit
B) The process audit finding of inactive oversight committee
C) The EU AI Act compliance documentation gaps
D) All three findings represent equal risk levels

<details>
<summary>Answer</summary>

**Correct: B**

The inactive oversight committee (process failure) is the ROOT CAUSE enabling the other issues. Without active governance, fairness gaps go undetected and compliance gaps persist. Fix the process failure first - it's the control failure that allows technical and compliance issues to occur and worsen. The exam tests understanding that governance process failures create systemic risk.

**Why the others are wrong:**
- While concerning, the 8% gap is only marginally above threshold and is a SYMPTOM. The inactive committee is WHY it wasn't caught and addressed earlier.
- Documentation gaps are compliance risks but don't directly cause harm. They're important but secondary to active governance failures that allow harmful models to operate unchecked.
- Risk levels differ significantly. Process failures (inactive oversight) create conditions for technical failures (fairness issues) and compliance failures (documentation). Not equal.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** An AI-powered content moderation system incorrectly flags and removes legitimate political speech from a social media platform, affecting thousands of users. The company's incident response team identifies the root cause as a human oversight failure - the content policy was updated but training data wasn't updated to reflect the new policy. Which documentation should be prioritized for regulatory inquiries about this incident?

A) Change management logs showing when the policy was updated and why training data wasn't synchronized
B) User complaints and appeals submitted about removed content
C) Performance metrics showing the system's overall accuracy rate
D) Legal analysis of whether the removed speech was actually protected

<details>
<summary>Answer</summary>

**Correct: A**

For a root cause of 'human oversight failure,' regulators will focus on PROCESS FAILURES in change management. Documentation proving what changed, when, who approved it, and why synchronization controls failed is critical evidence. This shows whether adequate processes existed and where they broke down - the core of a governance audit.

**Why the others are wrong:**
- User complaints document the harm but don't explain the root cause or process failure. They're evidence of impact, not of governance breakdown.
- Overall accuracy doesn't address the specific failure mode or process breakdown. High overall accuracy with systematic failures in one area may indicate inadequate monitoring.
- Legal analysis of content is about liability, not about the AI governance process failure that caused the incident. Different inquiry focus.

</details>

---

