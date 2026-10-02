## Chapter 2: AI Development Lifecycle and Documentation — Practice Questions

**Q1.** A European healthcare company is deploying an AI system to assist radiologists in detecting tumors from CT scans. The system will influence diagnostic decisions but final diagnosis remains with the radiologist. Under the EU AI Act, which documentation artifact is MANDATORY before deployment?

A) Model card with performance metrics and intended use cases
B) Fundamental Rights Impact Assessment (FRIA) as required by Article 27
C) Dataset datasheet documenting training data sources and demographics
D) Third-party vendor audit report with penetration testing results

<details>
<summary>Answer</summary>

**Correct: B**

Article 27 of the EU AI Act mandates Fundamental Rights Impact Assessments (FRIAs) for high-risk AI systems before deployment. Medical diagnosis assistance qualifies as high-risk under Annex III. The FRIA must assess impact on fundamental rights including health, privacy, and non-discrimination. This is a legal requirement, not optional best practice.

**Why the others are wrong:**
- Model cards are best practice (Mitchell et al. 2019) but not legally mandated by the EU AI Act. They're recommended for transparency but insufficient for compliance.
- Datasheets for datasets (Gebru et al. 2018) are valuable for documentation but not a specific EU AI Act Article 27 requirement. They support data governance but don't replace FRIA.
- Security audits address cybersecurity risks but Article 27 specifically requires fundamental rights assessment. Penetration testing doesn't evaluate bias, discrimination, or rights impact.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During the validation stage of an AI development lifecycle, performance metrics show 94% accuracy on the test set but 78% accuracy on a held-out dataset from a different geographic region. What is the MOST appropriate next action before deployment?

A) Deploy the model since 78% exceeds the 75% minimum threshold for production systems
B) Investigate data representativeness and collect additional training data from underrepresented regions
C) Retrain the model on the combined test and held-out datasets to improve generalization
D) Document the performance gap in the model card and proceed with deployment to the original region only

<details>
<summary>Answer</summary>

**Correct: B**

The 16-point accuracy drop indicates the training data lacks geographic representativeness. Data quality requirements mandate that training data must represent the deployment population. This is a data collection/preparation issue that must be fixed before deployment. The lifecycle should loop back to data collection stage to gather representative samples.

**Why the others are wrong:**
- There is no universal '75% threshold' — performance requirements depend on use case and risk level. The issue is distribution shift, not absolute accuracy. Deploying would risk systematic bias against the underrepresented region.
- Using test data for training violates fundamental ML principles (data leakage) and would invalidate all performance metrics. The test set must remain unseen. This doesn't address the root cause of non-representative training data.
- Documenting limitations is necessary but insufficient. Limiting deployment doesn't solve the representativeness problem if the system will eventually serve other regions. The model fundamentally fails validation for broader deployment.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** An organization is procuring a third-party large language model API for customer service automation. Which contractual clause provides the STRONGEST protection against liability if the model generates discriminatory responses?

A) Service Level Agreement (SLA) guaranteeing 99.9% uptime with financial penalties for downtime
B) Indemnification clause where vendor assumes liability for AI-generated outputs that violate anti-discrimination laws
C) Audit rights allowing the organization to review the vendor's model training data annually
D) Data processing agreement (DPA) ensuring GDPR compliance for customer data handling

<details>
<summary>Answer</summary>

**Correct: B**

Indemnification clauses explicitly allocate liability risk. For third-party model procurement, vendor indemnification for discriminatory outputs transfers legal and financial risk to the vendor. This is the strongest contractual protection because it makes the vendor financially responsible for harm caused by their model's outputs.

**Why the others are wrong:**
- SLAs address availability, not output quality or discrimination. Uptime guarantees don't protect against harmful content generation. A discriminatory model with 99.9% uptime still creates liability.
- Audit rights provide transparency but don't transfer liability. Discovering bias through audits doesn't prevent it or shift legal responsibility. Audits are detective controls, not liability shields.
- DPAs address data privacy compliance but don't cover AI output liability. GDPR violations are separate from anti-discrimination law violations. A DPA doesn't protect if the model's responses discriminate.

</details>

---

**Q4.** A financial institution deploys a credit scoring AI model. Six months post-deployment, continuous monitoring detects that approval rates for applicants aged 18-25 have dropped from 42% to 31% while approval rates for other age groups remain stable. Training data approval rates for 18-25 year olds was 41%. What does this indicate?

A) Normal model behavior reflecting changing economic conditions for younger applicants
B) Performance degradation likely due to concept drift requiring model retraining
C) Data poisoning attack targeting the model's age-related features
D) Successful bias mitigation as the model corrects for historical over-approval

<details>
<summary>Answer</summary>

**Correct: B**

This is textbook concept drift. The model's behavior for one demographic segment has changed significantly (42%→31%) while training data showed 41% and other groups remain stable. This indicates the relationship between features and creditworthiness has shifted for this age group (concept drift), not that input distributions changed (data drift). Continuous monitoring detected performance degradation requiring lifecycle return to model development/retraining stage.

**Why the others are wrong:**
- If economic conditions changed, all age groups would show impact, not just 18-25. The stable performance for other groups contradicts this explanation. Also, monitoring should detect legitimate economic shifts as expected behavior, not degradation.
- Data poisoning would show sudden performance changes, manipulation attempts, or adversarial patterns. Gradual drift over 6 months affecting one demographic is consistent with concept drift, not attack. No evidence of malicious data injection.
- Bias mitigation aims to equalize opportunity, not reduce approval rates for one group only. If this were mitigation, rates should shift to match other groups or training data. The drop below training baseline (41%→31%) indicates degradation, not correction.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** During the problem definition stage of an AI project, stakeholders propose using AI to automate hiring decisions to 'remove human bias.' As the AI governance lead, which concern should you raise FIRST?

A) Automated hiring decisions may constitute high-risk AI under EU AI Act requiring conformity assessment
B) The training data for hiring models will likely encode historical hiring biases from past decisions
C) The problem definition assumes AI is less biased than humans, which requires validation
D) Deployment will require extensive monitoring infrastructure to detect discriminatory patterns

<details>
<summary>Answer</summary>

**Correct: A**

Problem definition stage must establish legal and regulatory feasibility BEFORE technical considerations. EU AI Act Annex III classifies AI for employment decisions (recruiting, selection) as high-risk AI requiring conformity assessment, third-party evaluation, and strict governance. This fundamentally shapes whether/how the project proceeds. Legal compliance constraints must be identified at problem definition, not later stages.

**Why the others are wrong:**
- While true that training data encodes bias, this is a data collection stage concern. Problem definition must first establish if the project is legally viable. You can address data bias only if the use case is permissible.
- Questioning the bias assumption is important but secondary to legal compliance. Even if AI could be proven less biased, high-risk AI classification still applies and constrains the project. Assumptions are validated after legal feasibility.
- Monitoring is a deployment/post-deployment stage concern. Problem definition must resolve whether the use case is permissible and feasible before worrying about monitoring architecture. Lifecycle stages have dependencies.

</details>

---

**Q6.** A model card for a facial recognition system states: 'Accuracy: 96% overall. Performance by skin tone: Fitzpatrick I-II: 98%, III-IV: 95%, V-VI: 89%.' The deployment context is airport security screening. What is the PRIMARY governance concern?

A) The overall 96% accuracy is below the 99% threshold required for security applications
B) Disaggregated performance metrics reveal disparate impact with 9-point accuracy gap across skin tones
C) The model card does not specify which dataset was used for performance evaluation
D) Fitzpatrick scale categorization may not align with how airport passengers self-identify

<details>
<summary>Answer</summary>

**Correct: B**

Model cards must surface disparate impact. The 9-point gap (98% vs 89%) means darker-skinned individuals face higher false rejection or false acceptance rates. In security screening, this creates systematic discrimination in scrutiny levels. Disaggregated metrics exist precisely to identify such disparities. This represents unequal treatment and violates fairness principles for high-stakes applications.

**Why the others are wrong:**
- There is no universal '99% threshold' for security. Required accuracy depends on specific use case, risk tolerance, and consequences of errors. The issue isn't overall accuracy but disparate accuracy across protected groups.
- While dataset documentation is important model card content, it's secondary to the disparate impact already revealed. Knowing the test dataset doesn't resolve the 9-point performance gap that constitutes discrimination.
- Self-identification vs. algorithmic categorization is a valid concern but secondary. Even if categorization were perfect, the 9-point performance gap still indicates the model performs worse for darker skin tones, creating discriminatory outcomes.

</details>

---

**Q7.** An AI system owner is establishing roles and accountability for a high-risk customer churn prediction model. Who should be assigned PRIMARY accountability for ensuring continuous monitoring detects performance degradation post-deployment?

A) Data scientists who developed the model, as they understand its technical characteristics
B) MLOps/DevOps engineers responsible for production infrastructure and monitoring systems
C) Business unit deploying the model, as they own the customer relationships and outcomes
D) AI governance officer who oversees compliance with organizational AI policies

<details>
<summary>Answer</summary>

**Correct: C**

Post-deployment accountability rests with the business unit deploying and using the model. They own the outcomes, observe real-world performance, and bear responsibility for decisions based on model outputs. While data scientists built it and MLOps monitors infrastructure, the business unit must ensure monitoring aligns with business KPIs and act on degradation. Lifecycle accountability shifts from builders to operators/users at deployment.

**Why the others are wrong:**
- Data scientists move to new projects post-deployment. While they may support monitoring design, they don't have ongoing accountability for production performance. Their role is consultative after handoff, not primary accountability.
- MLOps engineers implement monitoring infrastructure but don't define what constitutes degradation in business context. They maintain systems but don't own business outcomes or decision-making on model performance acceptability.
- Governance officers provide oversight and ensure compliance, but they don't have PRIMARY accountability for operational monitoring. Their role is assurance and policy enforcement, not day-to-day performance management. They audit, not operate.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** A company is conducting vendor due diligence for a third-party computer vision API. The vendor provides model accuracy metrics but refuses to disclose training data sources citing 'proprietary information.' What is the MOST significant procurement risk this creates?

A) Inability to verify if training data includes copyrighted images, creating IP infringement liability
B) Lack of transparency prevents assessment of data representativeness and potential systematic biases
C) Missing information makes it impossible to compare this vendor's data quality to competitors
D) Violation of EU AI Act transparency requirements for high-risk AI system documentation

<details>
<summary>Answer</summary>

**Correct: B**

For procurement due diligence, the primary risk is inability to assess if the model will perform fairly and accurately for your use case. Unknown training data means you cannot evaluate representativeness for your deployment population or detect systematic biases that could cause discriminatory outcomes. This creates operational and legal risk as you deploy a 'black box' that may fail for specific demographics or scenarios.

**Why the others are wrong:**
- IP/copyright risk exists but is secondary to performance and bias risk. Many vendors use licensed or proprietary data legally. Without knowing your specific use case risk level, bias assessment is more fundamental to procurement decisions than IP concerns.
- Competitive comparison is a business consideration but not the most significant risk. You can compare vendors on other factors (accuracy, pricing, SLAs). The inability to assess bias and representativeness creates compliance and fairness risks, not just competitive disadvantage.
- EU AI Act transparency requirements depend on whether the use case is high-risk. The question doesn't specify high-risk classification. Even if applicable, the immediate risk is deploying a potentially biased model, not regulatory documentation compliance.

</details>

---

