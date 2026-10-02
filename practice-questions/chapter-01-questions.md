## Chapter 1: Foundations of AI Systems for Governance — Practice Questions

**Q1.** A company develops a large language model and licenses it to a healthcare provider who integrates it into their patient triage system. Under the EU AI Act, who is responsible for ensuring the deployed system meets high-risk AI requirements including bias testing and human oversight?

A) The model developer (provider) is solely responsible since they created the AI model
B) The healthcare provider (deployer) is solely responsible for the deployed system's compliance
C) Both share responsibility: provider for the model's capabilities, deployer for the system's safe deployment and monitoring
D) The importer is responsible if the model was developed outside the EU

<details>
<summary>Answer</summary>

**Correct: C**

EU AI Act Articles 16 and 26 establish distinct obligations for providers (ensuring model meets requirements) and deployers (ensuring appropriate deployment, monitoring, and human oversight). Both have compliance obligations for high-risk AI systems.

**Why the others are wrong:**
- Provider responsibility doesn't end at model delivery - they must ensure model capabilities meet requirements, but can't control deployment context
- Deployer can't be solely responsible for model characteristics they didn't create - provider retains obligations for model safety and performance
- Importer role (Article 23) applies when bringing AI systems into EU market, but doesn't override provider-deployer split for domestically developed systems

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An organization is documenting their AI governance framework. They need to distinguish between 'AI model' and 'AI system' per 2026 AIGP Body of Knowledge. Which statement correctly captures this distinction?

A) AI model and AI system are interchangeable terms - both refer to the trained algorithm
B) AI model is the trained algorithm; AI system includes the model plus data pipelines, interfaces, deployment infrastructure, and monitoring
C) AI system is only the cloud infrastructure that hosts the model
D) AI model includes training data; AI system is just the inference component

<details>
<summary>Answer</summary>

**Correct: B**

2026 BoK emphasizes AI system as the complete deployed solution encompassing model, data infrastructure, user interfaces, APIs, monitoring systems, and operational environment. This distinction is critical for governance because risks emerge from the entire system, not just the model.

**Why the others are wrong:**
- Terms are not interchangeable - exam specifically tests understanding that model is one component of a larger system
- Infrastructure is part of the system but system includes much more: data flows, model, interfaces, governance controls
- Training data is an input to model creation; AI system encompasses both training and inference infrastructure plus operational components

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A European retailer purchases a general-purpose AI system (GPAI) developed in the United States and deploys it for automated hiring decisions without modification. Under EU AI Act Article 23, what are the retailer's primary obligations as an importer?

A) Ensure the system bears CE marking, verify provider's conformity assessment was completed, maintain technical documentation, and register as a high-risk AI system deployer
B) Only register the system with EU authorities - compliance is the US provider's responsibility
C) Conduct full conformity assessment as if they were the provider since the original provider is outside EU jurisdiction
D) Importers have no obligations for GPAI systems - only for specialized AI applications

<details>
<summary>Answer</summary>

**Correct: A**

Article 23 places specific obligations on importers: verify CE marking exists, ensure conformity assessment documentation is available, maintain records, and comply with deployer obligations when using high-risk AI. Importers act as gatekeepers for non-EU AI entering the market.

**Why the others are wrong:**
- Importers cannot delegate verification responsibilities - they must actively ensure compliance documentation exists
- Importers don't repeat the provider's conformity assessment but must verify it was properly completed and documented
- Article 23 explicitly applies to importers regardless of AI type - GPAI systems used in high-risk applications face the same import requirements

</details>

---

**Q4.** A financial institution is implementing an AI system for loan approvals. The governance team needs to understand data governance differences. Which scenario correctly describes the distinction between training data governance and inference data governance?

A) Training data requires bias testing and representativeness validation; inference data requires monitoring for data drift and input validation to detect adversarial inputs
B) Training data and inference data have identical governance requirements - both need the same privacy protections
C) Training data governance focuses on volume and storage costs; inference data governance focuses on prediction accuracy
D) Only training data needs governance controls; inference data is outside the model so requires no special governance

<details>
<summary>Answer</summary>

**Correct: A**

Training data governance focuses on dataset quality, representativeness, bias detection, and fairness during model development. Inference data governance focuses on ongoing monitoring for distribution drift, input validation, adversarial attack detection, and ensuring real-world inputs match training assumptions. Both are critical but address different risks.

**Why the others are wrong:**
- Privacy applies to both, but training data needs additional controls for bias/representativeness while inference needs drift monitoring - requirements differ
- Volume and cost are operational concerns, not governance distinctions - exam tests understanding of risk-based governance differences
- Inference data governance is critical - poor input data quality, drift, or adversarial inputs can cause model failures even if model is well-trained

</details>

---

**Q5.** During an audit, governance professionals must explain the difference between supervised learning and reinforcement learning. Which statement best captures the governance implications of this distinction?

A) Supervised learning uses labeled training data and requires data quality governance; reinforcement learning learns from environmental feedback and requires safety constraints on exploration to prevent harmful trial-and-error in production
B) Supervised learning doesn't need human oversight; reinforcement learning requires constant human monitoring
C) The distinction is purely technical with no governance implications - both are just machine learning approaches
D) Supervised learning is always higher risk because it uses more data

<details>
<summary>Answer</summary>

**Correct: A**

Supervised learning governance focuses on training data quality, labeling accuracy, and bias in labeled datasets. Reinforcement learning governance must address exploration risks (agent trying potentially harmful actions), reward function alignment, and safe experimentation bounds. The learning mechanism directly impacts risk profile.

**Why the others are wrong:**
- Both need human oversight - supervised learning needs oversight of training data and labels; reinforcement learning needs oversight of reward functions and action boundaries
- Learning approach fundamentally changes risk profile and required controls - this is a core governance consideration tested on exam
- Risk depends on application and deployment context, not data volume - reinforcement learning may use less data but pose higher real-time safety risks

</details>

---

**Q6.** An AI ethics committee is evaluating a foundation model (large language model with 175B parameters) that will be fine-tuned for multiple use cases. What characteristic of foundation models most impacts governance strategy compared to task-specific models?

A) Foundation models are always open source so governance focuses on community contributions
B) Foundation models are pre-trained on broad data and adapted for multiple tasks, requiring governance at both the base model level and each downstream use case
C) Foundation models only need governance during initial training; fine-tuning is low-risk
D) Foundation models are too complex to govern effectively - governance focuses only on simpler models

<details>
<summary>Answer</summary>

**Correct: B**

Foundation models' multi-purpose nature creates dual governance needs: base model governance (training data, capabilities, known limitations) and use-case specific governance (fine-tuning data, application context, deployment risks). Risks can emerge from either base model or adaptation layer.

**Why the others are wrong:**
- Foundation models can be proprietary or open source - licensing model doesn't define governance requirements, capabilities and risks do
- Fine-tuning can introduce new risks (bias in fine-tuning data, capability misalignment) - both stages need governance
- Complexity increases governance importance, not decreases it - foundation models require sophisticated governance frameworks precisely because of their broad capabilities

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A distributor makes an AI-powered medical diagnostic system available on their marketplace platform. The system was developed by a provider in Germany and will be sold to hospitals across the EU. Under EU AI Act Article 24, what is the distributor's primary obligation before making the system available?

A) Conduct independent testing to verify the system's medical accuracy
B) Verify that the system has required CE marking and that provider/importer has fulfilled their obligations; ensure proper storage and transport conditions that preserve compliance
C) Rewrite the system's technical documentation in all EU languages
D) Distributors have no obligations - only providers and deployers face EU AI Act requirements

<details>
<summary>Answer</summary>

**Correct: B**

Article 24 requires distributors to verify CE marking exists, check that provider/importer completed their obligations, maintain proper storage/transport conditions, and cooperate with authorities. Distributors are gatekeepers who prevent non-compliant AI from reaching market but don't repeat technical assessments.

**Why the others are wrong:**
- Independent testing is provider's responsibility during conformity assessment - distributor verifies it was done, not redo it
- Documentation must exist but distributor isn't responsible for translation - they verify required documentation is available
- Article 24 explicitly establishes distributor obligations - exam heavily tests understanding of all actor roles

</details>

---

**Q8.** A governance professional is mapping AI lifecycle actors for a cross-border AI deployment. Company A (US) develops the base model. Company B (France) fine-tunes it for EU market. Company C (Germany) integrates it into their HR system. Company D (Netherlands) sells the HR system to employers. Under EU AI Act, which role assignment is correct?

A) A=Provider, B=Deployer, C=Deployer, D=Distributor
B) A=Provider, B=Importer, C=Provider, D=Distributor
C) A=Importer, B=Provider, C=Deployer, D=Distributor
D) A=Provider (model), B=Importer and Provider (system), C=Deployer, D=Distributor

<details>
<summary>Answer</summary>

**Correct: D**

Company A is provider of the base model. Company B imports the model into EU (importer) and creates a new AI system through fine-tuning (provider of that system). Company C deploys the system in their operations (deployer). Company D makes it available on market (distributor). One entity can have multiple roles.

**Why the others are wrong:**
- Company B fine-tunes and creates new AI system for EU market, making them provider of that system, not just deployer; also they import the base model
- Company A developed model outside EU - B brings it into EU market (importer role); C doesn't develop or substantially modify, only deploys
- Company A developed the original model (provider role); they're outside EU but that doesn't make them importer - B imports their model

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

