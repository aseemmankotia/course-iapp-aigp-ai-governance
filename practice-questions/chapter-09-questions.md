## Chapter 9: EU AI Act Part 2: High-Risk Compliance & Global AI Laws — Practice Questions

**Q1.** A European company is deploying a high-risk AI system for credit scoring. According to the EU AI Act, which Article 10 data governance requirement must they implement?

A) Use only publicly available datasets to avoid GDPR complications
B) Implement data quality checks including examining biases, identifying gaps, and ensuring statistical relevance and completeness
C) Store all training data for 10 years minimum regardless of data minimization principles
D) Obtain explicit consent from all individuals whose data appears in training datasets

<details>
<summary>Answer</summary>

**Correct: B**

Article 10 specifically requires high-risk AI providers to implement data governance practices that include examining training/validation/testing datasets for biases, identifying data gaps, ensuring datasets are relevant, representative, free of errors, and complete. This ensures data quality and appropriateness for the intended purpose.

**Why the others are wrong:**
- Public datasets can still contain biases and quality issues; Article 10 requires data governance regardless of source, not avoidance of certain data types
- 10-year retention contradicts GDPR's data minimization and storage limitation principles; the EU AI Act requires appropriate retention, not arbitrary long periods
- Explicit consent is one legal basis under GDPR but not required for all AI training; legitimate interest (Article 6(1)(f)) is often used, and Article 10 doesn't mandate consent for high-risk AI data governance

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An AI provider has developed a biometric identification system for law enforcement. Which conformity assessment procedure applies under the EU AI Act?

A) Internal conformity assessment following Annex VI, then self-issue CE marking
B) Third-party assessment by a notified body following Annex VII, then CE marking after approval
C) No conformity assessment needed; law enforcement systems are exempt from EU AI Act
D) Conformity assessment only if the system is deployed EU-wide, not for single-country use

<details>
<summary>Answer</summary>

**Correct: B**

Biometric identification systems are specifically listed as requiring third-party notified body assessment under Annex VII. This is one of the few high-risk AI categories that cannot use internal assessment due to heightened risks to fundamental rights.

**Why the others are wrong:**
- Annex VI internal assessment is for most high-risk AI systems, but biometric identification and critical infrastructure explicitly require Annex VII third-party notified body assessment
- Law enforcement AI systems are subject to the EU AI Act; they fall under high-risk category and have specific requirements in Title III
- Conformity assessment requirements apply regardless of deployment scope; geographic deployment doesn't change the conformity procedure required

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A company's high-risk AI system made an automated decision rejecting a loan application. Under GDPR Article 22 and the EU AI Act intersection, what must the company provide?

A) Only the AI's confidence score and final decision, no human involvement needed if accuracy exceeds 95%
B) Human oversight capability (Article 14), transparency to the deployer (Article 13), and meaningful information about the logic involved per GDPR Article 22
C) Complete source code and training data access to the applicant upon request
D) Annual audit reports from a third-party notified body certifying the decision was fair

<details>
<summary>Answer</summary>

**Correct: B**

The intersection requires: EU AI Act Article 14 human oversight (humans can intervene in automated decisions), Article 13 transparency to deployers, and GDPR Article 22 rights including meaningful information about the logic, significance, and consequences. All three work together for automated decisions with legal/significant effects.

**Why the others are wrong:**
- GDPR Article 22 prohibits solely automated decisions with legal/significant effects without human intervention; no accuracy threshold exempts from human oversight requirement
- Neither GDPR nor EU AI Act require complete source code/training data disclosure; transparency obligations are about logic and decision factors, not full technical disclosure
- Annual third-party audits are not required for all high-risk AI; most use Annex VI internal assessment, and ongoing audits aren't mandated by Article 22 intersection

</details>

---

**Q4.** Under EU AI Act Article 12, a high-risk AI system must maintain logs that are automatically generated. What is the minimum retention period for these logs?

A) 6 months to align with GDPR data subject request timelines
B) As appropriate for the intended purpose, considering applicable legal obligations and the state of the art
C) 5 years from the date of generation to cover product liability claims
D) Permanently, as logs are essential evidence for post-market monitoring

<details>
<summary>Answer</summary>

**Correct: B**

Article 12 states logs must be kept for 'an appropriate period' considering the intended purpose and applicable legal obligations. The Act intentionally doesn't specify fixed timeframes, allowing context-appropriate retention while respecting GDPR storage limitation.

**Why the others are wrong:**
- 6 months is too rigid; Article 12 doesn't specify this timeframe and some use cases require longer or shorter retention based on context and legal obligations
- 5 years is not mandated by Article 12; the retention period must be appropriate for purpose, not tied to general product liability timeframes
- Permanent retention violates GDPR's storage limitation principle; logs containing personal data must be deleted when no longer needed for their purpose

</details>

---

**Q5.** A Colorado-based company uses AI to make consequential decisions about employment. Which compliance requirement applies under the Colorado AI Act (effective 2026)?

A) Conduct impact assessments for high-risk AI systems, provide notice to consumers, and offer opt-out mechanisms for consequential decisions
B) Obtain FTC pre-approval before deploying AI in employment contexts
C) Register all AI systems with the Colorado AI Registry within 30 days of deployment
D) Use only AI systems that have received CE marking from EU notified bodies

<details>
<summary>Answer</summary>

**Correct: A**

The Colorado AI Act (effective February 2026) requires developers and deployers to conduct impact assessments for high-risk AI, provide notice to consumers about AI use in consequential decisions (employment, housing, credit, etc.), and offer opt-out or alternative process options.

**Why the others are wrong:**
- The FTC doesn't have pre-approval authority for AI systems; the FTC uses existing consumer protection laws (Section 5 unfair/deceptive practices) for enforcement, not a pre-approval regime
- Colorado doesn't require an AI registry system; the law focuses on impact assessments, transparency, and consumer rights, not registration
- CE marking is an EU requirement under the EU AI Act; US state laws don't require EU conformity marking, and Colorado has its own compliance framework

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** When conducting a GDPR Data Protection Impact Assessment (DPIA) for high-risk AI processing under Article 35, which element is mandatory?

A) Pre-deployment approval from the relevant supervisory authority in all cases
B) Systematic description of processing operations, necessity assessment, and measures to address risks including safeguards
C) Third-party audit by an independent AI ethics board certified by the European Data Protection Board
D) Publication of the DPIA summary in the EU's Transparency Register within 60 days

<details>
<summary>Answer</summary>

**Correct: B**

GDPR Article 35(7) mandates DPIAs contain: systematic description of processing and purposes, assessment of necessity and proportionality, assessment of risks to rights/freedoms, and measures to address risks including safeguards, security measures, and mechanisms to ensure protection.

**Why the others are wrong:**
- Prior consultation with supervisory authority (Article 36) is only required when DPIA indicates high risk that can't be mitigated; not all DPIAs require authority approval, only those with residual high risks
- Third-party audits by ethics boards aren't mandated by GDPR Article 35; DPIAs can be conducted internally with optional DPO consultation, no mandatory external ethics audit
- GDPR doesn't require public DPIA disclosure or an EU Transparency Register for DPIAs; DPIAs are internal accountability documents, though summaries may be shared with authorities upon request

</details>

---

**Q7.** A company trains a generative AI model on personal data scraped from the internet. Under GDPR, which legal basis is most commonly used for AI training data processing?

A) Explicit consent (Article 6(1)(a)) from each individual whose data was scraped
B) Legitimate interest (Article 6(1)(f)) balanced against individuals' rights, with appropriate safeguards
C) Performance of a contract (Article 6(1)(b)) between the company and data subjects
D) Legal obligation (Article 6(1)(c)) under the EU AI Act to train AI on diverse datasets

<details>
<summary>Answer</summary>

**Correct: B**

Legitimate interest (Article 6(1)(f)) is most commonly used for AI training because: consent is impractical for large-scale web scraping, companies must conduct legitimate interest assessments (LIA) balancing innovation against privacy rights, and implement safeguards like anonymization, access controls, and transparency measures.

**Why the others are wrong:**
- Explicit consent is impractical for scraped data where individuals haven't been directly contacted; while consent is valid, it's rarely feasible for large-scale training data collection from public sources
- Performance of contract requires an actual contract with the data subject; web scraping victims have no contractual relationship with the scraper, so Article 6(1)(b) doesn't apply
- The EU AI Act doesn't create a legal obligation to train on specific datasets; Article 6(1)(c) requires an actual EU/Member State law mandating processing, which doesn't exist for AI training diversity

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** Under the NIST AI Risk Management Framework (AI RMF), which function is NOT one of the four core functions?

A) Govern
B) Map
C) Measure
D) Monitor

<details>
<summary>Answer</summary>

**Correct: D**

Monitor is not one of NIST AI RMF's four core functions. The four functions are: Govern (culture and oversight), Map (context and risks), Measure (assess and benchmark), and Manage (prioritize and respond to risks). Monitoring is incorporated within Manage function, not a separate core function.

**Why the others are wrong:**
- Govern IS a core function: establishes and nurtures a culture of risk management, including governance structures, policies, and accountability
- Map IS a core function: establishes context, categorizes AI system, and identifies potential impacts and risks
- Measure IS a core function: employs tools and methodologies to assess, analyze, and track AI risks and impacts

</details>

---

