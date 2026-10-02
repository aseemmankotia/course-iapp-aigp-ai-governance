## Chapter 6: ISO/IEC 42001 and AI Governance Programs — Practice Questions

**Q1.** A multinational corporation is preparing for ISO/IEC 42001 certification. During the Clause 4 assessment, the team identifies employees, customers, regulators, and AI system developers as interested parties. Which activity is MOST critical to complete next according to ISO/IEC 42001 requirements?

A) Document the AI policy statement and obtain C-suite approval
B) Determine the needs and expectations of these interested parties as they relate to the AI management system
C) Conduct a comprehensive risk assessment of all AI systems in production
D) Establish an AI system inventory with system IDs and risk tiers

<details>
<summary>Answer</summary>

**Correct: B**

Clause 4 specifically requires understanding interested parties AND determining their needs and expectations related to the AI management system. This is a prerequisite before moving to later clauses like policy establishment (Clause 5) or planning (Clause 6).

**Why the others are wrong:**
- AI policy establishment occurs in Clause 5 (Leadership), which comes after completing Clause 4 requirements
- Risk assessment is part of Clause 6 (Planning), which follows after context establishment in Clause 4
- AI system inventory is an operational control (Clause 8), not a Clause 4 requirement focused on organizational context

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An organization's AI system inventory contains the following entry: System ID: CR-2024-089 | Use Case: Credit risk scoring | Risk Tier: High | Data Sources: Credit bureau data, transaction history | Owner: Risk Management VP. What critical element is MISSING that ISO/IEC 42001 operational controls require?

A) Model architecture and algorithm type
B) Accountability assignment for the AI system
C) Third-party audit completion date
D) ISO/IEC 42001 Annex A control mappings

<details>
<summary>Answer</summary>

**Correct: B**

ISO/IEC 42001 requires AI system inventories to include clear accountability assignments (who is responsible for decisions, oversight, outcomes). While 'Owner' is listed, accountability must explicitly cover decision-making authority, not just administrative ownership.

**Why the others are wrong:**
- Model architecture details are useful but not mandatory inventory fields under ISO/IEC 42001 baseline requirements
- Audit dates are part of conformity assessment processes (Clause 9), not core inventory documentation requirements
- Annex A control mappings are risk treatment documentation, not inventory contents; they link to systems but aren't inventory fields

</details>

---

**Q3.** A healthcare AI vendor is developing a clinical decision support system that will be classified as high-risk under the EU AI Act. They want to demonstrate conformance with AI governance standards. Which approach BEST meets both ISO/IEC 42001 certification and EU AI Act conformity assessment requirements?

A) Conduct annual self-assessments against ISO/IEC 42001 requirements and maintain internal audit logs
B) Engage a notified body to assess EU AI Act compliance, then separately pursue ISO/IEC 42001 certification through an accredited body
C) Complete ISO/IEC 42001 certification first, then claim presumption of conformity for all EU AI Act requirements
D) Use ISO/IEC 42001 certification by an accredited body as part of the conformity assessment, supplemented by notified body review of EU AI Act-specific requirements

<details>
<summary>Answer</summary>

**Correct: D**

EU AI Act allows harmonized standards like ISO/IEC 42001 to create presumption of conformity for overlapping requirements. High-risk systems still need notified body involvement for EU-specific requirements, but ISO/IEC 42001 certification addresses governance foundation. This integrated approach is most efficient.

**Why the others are wrong:**
- Self-assessments don't provide third-party certification required for ISO/IEC 42001 nor satisfy EU AI Act notified body requirements for high-risk systems
- Separate processes create redundancy; ISO/IEC 42001 can be leveraged within EU AI Act conformity assessment rather than treated as entirely separate
- ISO/IEC 42001 creates presumption of conformity for governance aspects but doesn't cover all EU AI Act technical requirements (e.g., specific documentation, transparency obligations)

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** During Clause 6 planning activities, an AI team must establish objectives for their facial recognition system used in physical security. The team proposes: 'Achieve 99.5% accuracy across all demographic groups by Q4 2026.' According to ISO/IEC 42001, what is the PRIMARY deficiency in this objective?

A) The objective doesn't specify how it will be monitored and measured
B) Accuracy metrics alone don't address AI-specific risks like bias, transparency, or data protection
C) The timeline is too aggressive for meaningful improvement in fairness metrics
D) The objective should reference specific Annex A controls that will be implemented

<details>
<summary>Answer</summary>

**Correct: B**

ISO/IEC 42001 Clause 6 requires objectives to consider AI-specific risks identified in risk assessment. Technical performance (accuracy) is necessary but insufficient; objectives must address risks like fairness, accountability, transparency depending on the system's risk profile. Facial recognition has well-known bias risks requiring explicit objectives.

**Why the others are wrong:**
- While monitoring is important, the fundamental issue is that the objective ignores identified AI risks beyond technical performance
- Timeline aggressiveness is a practical concern but not the primary ISO/IEC 42001 deficiency; objectives must address risk areas first
- Objectives don't need to reference specific Annex A controls; controls are selected during risk treatment planning, not embedded in objectives

</details>

---

**Q5.** A financial services company operates 47 AI systems. During ISO/IEC 42001 implementation, they categorize systems into risk tiers. System A processes loan applications (high-risk), System B generates marketing email subject lines (low-risk). How should the AI system inventory documentation differ between these systems according to proportionate governance principles?

A) Both systems require identical inventory documentation; ISO/IEC 42001 doesn't allow reduced documentation for low-risk systems
B) System A requires full Annex A control documentation; System B only needs basic system ID and use case description
C) Both require core inventory fields (ID, use case, risk tier, data sources, accountability), but System A requires more detailed risk assessment and control documentation
D) System B can be excluded from the inventory entirely if annual risk assessments confirm it remains low-risk

<details>
<summary>Answer</summary>

**Correct: C**

ISO/IEC 42001 requires all AI systems to be in the inventory with core fields, but allows proportionate application of controls based on risk. Both systems need baseline documentation, but high-risk systems require more extensive risk assessment documentation and control implementation records. This is risk-based governance in practice.

**Why the others are wrong:**
- ISO/IEC 42001 explicitly supports proportionate approaches based on risk; requiring identical documentation for all systems is inefficient and not required
- Even low-risk systems need core inventory documentation including accountability and data sources; the standard requires comprehensive inventory regardless of risk level
- All AI systems must be in the inventory; exclusion violates ISO/IEC 42001 requirements for comprehensive AI system oversight

</details>

---

**Q6.** An organization's leadership team (Clause 5) is establishing an AI policy for ISO/IEC 42001 compliance. The draft policy states: 'We commit to ethical AI development and deployment in accordance with industry best practices.' What is the MOST significant deficiency for certification purposes?

A) The policy doesn't specify roles and responsibilities for AI governance
B) The policy lacks commitment to continual improvement of the AI management system
C) The policy doesn't reference specific AI risks like bias, transparency, or accountability
D) The policy should be approved by the board of directors, not just leadership team

<details>
<summary>Answer</summary>

**Correct: B**

ISO/IEC 42001 Clause 5.2 explicitly requires the AI policy to include commitment to continual improvement of the AI management system. This is a mandatory element for certification. While the policy is vague in other ways, missing the continual improvement commitment is a direct violation of standard requirements.

**Why the others are wrong:**
- Roles and responsibilities are established separately in governance structures; the policy sets direction and commitments, not organizational charts
- While addressing specific risks is good practice, ISO/IEC 42001 policy requirements focus on commitments to the management system, compliance, and improvement rather than listing specific risk domains
- Top management approval is required, but 'leadership team' may constitute top management; the standard doesn't mandate board-level approval specifically

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A retailer is conducting AI risk assessment (Clause 6) for a new product recommendation system. The general enterprise risk framework rates this as 'Medium' risk based on revenue impact. However, the AI-specific risk assessment must also consider additional factors. Which factor is MOST important to include that general enterprise risk methodologies typically miss?

A) Potential for the system to perpetuate discriminatory patterns in recommendations based on protected characteristics
B) Cybersecurity vulnerabilities in the recommendation algorithm
C) Cloud infrastructure costs and scalability limitations
D) Competitive intelligence risks from reverse-engineering the model

<details>
<summary>Answer</summary>

**Correct: A**

AI-specific risk assessment must address algorithmic fairness, bias, and potential discriminatory impacts—risks that don't exist with traditional software. Recommendation systems can encode and amplify historical biases (e.g., showing certain products only to certain demographics). This is a quintessential AI-specific risk beyond traditional enterprise risk categories.

**Why the others are wrong:**
- Cybersecurity risks apply to all IT systems, not specific to AI; general enterprise risk frameworks already cover this
- Infrastructure and cost risks are standard business/IT risks covered by traditional enterprise risk management
- IP and competitive risks exist for any proprietary technology; this isn't AI-specific risk requiring special assessment methodology

</details>

---

**Q8.** An organization has implemented ISO/IEC 42001 controls and is preparing for a third-party certification audit. The auditor requests evidence of performance evaluation (Clause 9). Which set of evidence BEST demonstrates conformance with ongoing performance evaluation requirements?

A) Initial risk assessment documentation, AI policy approval memo, and organizational chart showing AI governance roles
B) Monthly AI system performance dashboards, quarterly management review meeting minutes, and internal audit reports from the past year
C) Complete AI system inventory, Annex A control implementation records, and employee training completion certificates
D) AI ethics committee charter, incident response procedures, and third-party penetration test results

<details>
<summary>Answer</summary>

**Correct: B**

Clause 9 (Performance Evaluation) requires monitoring, measurement, analysis, evaluation, internal audit, and management review. Monthly dashboards show monitoring, management reviews demonstrate leadership oversight, and internal audits prove systematic evaluation. These are ongoing performance evaluation activities, not one-time setup documentation.

**Why the others are wrong:**
- These are Clause 4-6 planning and setup documents, not evidence of ongoing performance evaluation and monitoring
- These are operational implementation records (Clause 8), not evidence of systematic performance evaluation processes
- These are governance structures and security controls, not evidence of the monitoring, analysis, and review activities required by Clause 9

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

