## Chapter 4: Privacy, Safety, and Societal Impacts of AI — Practice Questions

**Q1.** A healthcare company wants to train a machine learning model to predict patient readmission risk using data from 50 hospitals across different regions. Each hospital has strict data governance policies preventing patient data from leaving their premises. Which approach BEST allows model training while respecting these constraints?

A) Use differential privacy with epsilon=0.1 to anonymize all patient records, then centralize the data for training
B) Implement federated learning where each hospital trains on local data and only model updates are shared centrally
C) Generate synthetic patient data based on aggregate statistics from each hospital, then train centrally on the synthetic dataset
D) Apply homomorphic encryption to patient records so the central server can train on encrypted data

<details>
<summary>Answer</summary>

**Correct: B**

Federated learning is specifically designed for this scenario: model training occurs locally at each hospital on their own data, only model weights/gradients are shared centrally, and raw patient data never leaves hospital premises. This preserves data locality while enabling collaborative model training.

**Why the others are wrong:**
- Differential privacy protects aggregate outputs but still requires centralizing the data first, violating the data governance constraint that data cannot leave hospital premises
- Synthetic data generation loses fidelity for rare conditions and edge cases critical in healthcare; also doesn't solve the fundamental issue that hospitals won't share even aggregate statistics detailed enough to generate realistic synthetic data
- Homomorphic encryption allows computation on encrypted data but is computationally expensive for ML training at scale and still requires data to be transmitted to central server, violating data locality requirements

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A credit card company implements differential privacy when releasing statistics about spending patterns. They set epsilon=5.0 for their privacy budget. What does this configuration indicate?

A) Strong privacy protection with minimal data utility - individual records are well-protected but aggregate statistics may be noisy
B) Moderate privacy-utility tradeoff suitable for most commercial applications with some privacy protection
C) Weak privacy protection with high data utility - aggregate statistics are accurate but individual records have limited protection
D) Invalid configuration - epsilon values must be between 0 and 1 for differential privacy to provide mathematical guarantees

<details>
<summary>Answer</summary>

**Correct: C**

In differential privacy, higher epsilon values mean weaker privacy protection. Epsilon=5.0 is considered high/weak privacy protection. The privacy-utility tradeoff: lower epsilon (e.g., 0.1-1.0) = stronger privacy but noisier results; higher epsilon (e.g., 5.0+) = weaker privacy but more accurate aggregate statistics.

**Why the others are wrong:**
- This describes LOW epsilon values (e.g., epsilon=0.1-0.5). Epsilon=5.0 is the opposite - weak privacy, high utility
- Epsilon=5.0 is not moderate - it's on the weak end of the privacy spectrum. Moderate would be epsilon=1.0-2.0
- Epsilon can be any positive number; there's no upper limit of 1. Common ranges: strong privacy epsilon<1, moderate 1-3, weak >3. Epsilon=5.0 is valid but provides weak privacy guarantees

</details>

---

**Q3.** An AI-powered resume screening system at a tech company is found to recommend male candidates 75% of the time for engineering roles, despite a 50-50 gender split in the applicant pool. Historical hiring data shows 80% of previous engineering hires were male. Which statement BEST describes the legal and technical issue?

A) This is disparate treatment discrimination - the model explicitly uses gender as a decision factor and violates Title VII of the Civil Rights Act
B) This is disparate impact discrimination - even without using gender explicitly, the model produces discriminatory outcomes that may violate employment law and require business necessity justification
C) This is acceptable algorithmic fairness since the model reflects actual historical hiring patterns and business outcomes
D) This requires implementing federated learning to train the model separately on male and female candidate data to ensure equal representation

<details>
<summary>Answer</summary>

**Correct: B**

This is textbook disparate impact: the model produces discriminatory outcomes (75% male recommendations vs 50% applicant pool) even if gender isn't an explicit input feature. Under US employment law (Title VII) and EEOC guidelines, disparate impact is illegal unless the employer can prove business necessity. The 75/50 ratio creates a potential Four-Fifths Rule violation.

**Why the others are wrong:**
- Disparate treatment means intentionally treating people differently based on protected characteristics (explicit use of gender). Here, the discrimination likely comes from correlated features in historical data (disparate impact), not explicit gender-based decisions
- Training on biased historical data (80% male hires) perpetuates discrimination. Legal compliance requires the model NOT to replicate historical bias. The fact that it reflects past patterns doesn't make it legal - it makes it problematic
- Federated learning is a privacy-preserving training technique, not a bias mitigation technique. It doesn't address the fundamental issue of biased training data or discriminatory outcomes

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A bank deploys an AI system for mortgage lending decisions in the United States. The model uses 200 features including zip code, employment history, and credit score, but explicitly excludes race, gender, and religion. The model approves 65% of white applicants but only 40% of Black applicants with similar credit profiles. Which regulatory framework is MOST relevant?

A) GDPR Article 22 - automated decision-making rights require human review of all mortgage decisions
B) Equal Credit Opportunity Act (ECOA) and Regulation B - prohibit credit discrimination and require disparate impact analysis even when protected characteristics aren't direct inputs
C) Fair Credit Reporting Act (FCRA) - requires disclosure of credit scores used in lending decisions
D) Sarbanes-Oxley Act - requires financial institutions to maintain accurate records of algorithmic decision-making processes

<details>
<summary>Answer</summary>

**Correct: B**

ECOA and Regulation B are the primary US laws governing credit discrimination. They explicitly prohibit disparate impact in lending - even when protected characteristics aren't used as inputs, if outcomes show discrimination (65% vs 40% approval rates), the lender must prove business necessity. Regulators examine proxy variables (like zip code) that correlate with protected classes.

**Why the others are wrong:**
- GDPR applies in EU, not US mortgage lending. While GDPR Article 22 addresses automated decisions, ECOA is the specific US credit discrimination law that applies here
- FCRA governs credit reporting and disclosure requirements but doesn't specifically address lending discrimination. ECOA/Regulation B are the anti-discrimination statutes
- Sarbanes-Oxley focuses on corporate financial reporting and accounting fraud, not consumer lending discrimination or algorithmic fairness

</details>

---

**Q5.** A medical AI system provides clinical decision support for radiologists reviewing chest X-rays. The system highlights potential areas of concern but the radiologist makes the final diagnosis. The AI misses a small lung nodule that a radiologist also misses. In a subsequent malpractice lawsuit, how is liability MOST likely allocated?

A) The AI vendor bears full liability since the system failed to detect the nodule, constituting a defective product under strict liability
B) The radiologist bears primary liability as the licensed professional who made the final diagnostic decision; AI is a decision support tool, not a diagnostic device
C) Liability is split 50-50 between the radiologist and AI vendor since both contributed to the missed diagnosis
D) The hospital bears vicarious liability for deploying an insufficiently validated AI system for clinical use

<details>
<summary>Answer</summary>

**Correct: B**

In clinical decision support (CDS) systems, the licensed healthcare professional retains final decision-making authority and liability. The AI is an assistive tool, not a replacement for professional judgment. Medical malpractice law holds the physician responsible for diagnostic decisions. The key distinction: CDS provides recommendations; diagnostic AI makes autonomous decisions (different liability model).

**Why the others are wrong:**
- AI vendors generally aren't liable for missed diagnoses in CDS systems unless there's a specific defect or misrepresentation. The system is a tool assisting professional judgment, not making autonomous medical decisions. Product liability would require showing the AI was defective relative to its stated capabilities
- There's no automatic 50-50 split in medical liability. The radiologist as the licensed decision-maker bears primary responsibility. Liability splitting would require proving the AI vendor had specific negligence beyond the radiologist's professional duty
- While hospitals can face vicarious liability for physician employees, the primary issue here is the radiologist's diagnostic decision, not hospital-level deployment validation. Hospital liability would be secondary unless there were systemic validation failures

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** A company trains a facial recognition model and wants to test its robustness against adversarial attacks. Which scenario represents a model poisoning attack rather than an adversarial example attack?

A) Adding imperceptible noise to a test image that causes the model to misclassify a stop sign as a yield sign
B) Injecting mislabeled images into the training dataset so the model learns incorrect associations between faces and identities
C) Using gradient-based optimization to find minimal perturbations that fool the model at inference time
D) Creating synthetic faces using GANs that the model incorrectly classifies with high confidence

<details>
<summary>Answer</summary>

**Correct: B**

Model poisoning attacks compromise the training phase by injecting malicious or mislabeled data into the training set, causing the model to learn incorrect patterns. This is a training-time attack. The key distinction: poisoning corrupts the model during training; adversarial examples attack a trained model during inference.

**Why the others are wrong:**
- This is a classic adversarial example attack - modifying input at inference time to fool a trained model. It's a test-time attack, not training-time poisoning
- This describes generating adversarial examples using gradient-based methods (like FGSM or PGD). It's an inference-time attack on a trained model, not training data poisoning
- While synthetic faces might reveal model weaknesses, this isn't specifically model poisoning unless those synthetic faces were injected into training data with wrong labels. Testing on synthetic data is robustness evaluation, not poisoning

</details>

---

**Q7.** A retail company wants to analyze customer purchase patterns while protecting individual privacy. They consider two approaches: (1) differential privacy with epsilon=0.5 on the full dataset, or (2) federated learning across 100 store locations. Each store has 10,000 customer records. Which factor MOST strongly favors choosing differential privacy over federated learning?

A) The company needs to publish aggregate statistics (average purchase value, popular product categories) for investor reports and public transparency
B) Store locations have unreliable internet connectivity and limited local computational resources for model training
C) The company wants to train a complex deep learning model for personalized product recommendations requiring multiple training iterations
D) Privacy regulations require that individual customer purchase records never be transmitted between store locations

<details>
<summary>Answer</summary>

**Correct: A**

Differential privacy is designed for releasing privacy-preserving aggregate statistics and query results. With epsilon=0.5 (strong privacy), the company can safely publish statistics without revealing individual customer data. Federated learning is for model training, not statistical releases. For publishing aggregate insights, differential privacy is the appropriate technique.

**Why the others are wrong:**
- This favors federated learning, not differential privacy. Federated learning handles unreliable connectivity and limited local compute by design - models train locally, only updates are transmitted. Differential privacy doesn't address network/compute constraints
- This favors federated learning. Complex models requiring multiple iterations benefit from federated learning's distributed training approach. Differential privacy adds noise to outputs, which can hurt model quality - it's not optimized for iterative deep learning training
- This describes a scenario where federated learning shines - data locality requirements. Differential privacy still requires centralizing data first (then adding noise), so it doesn't solve the data transmission constraint

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** An e-commerce company uses AI to monitor warehouse workers and automatically flags workers whose packing speed falls below 95% of the team average for three consecutive hours. Flagged workers receive warnings, and three warnings in a month result in termination. Which AI governance concern is MOST critical?

A) Model interpretability - workers cannot understand how the AI calculates their performance metrics relative to team averages
B) Lack of human oversight - automated termination decisions without manager review violate principles of meaningful human control over significant decisions affecting employment
C) Data privacy - continuous monitoring and performance tracking may violate worker privacy rights under GDPR or state privacy laws
D) Algorithmic bias - the performance metric may have disparate impact on workers with disabilities or protected characteristics

<details>
<summary>Answer</summary>

**Correct: B**

Automated termination without meaningful human review is the most critical issue. Employment decisions are high-stakes, and AI governance best practices (and many laws) require human oversight for decisions affecting livelihoods. The system creates an automated path from measurement to termination, removing human judgment about context, extenuating circumstances, or errors.

**Why the others are wrong:**
- While interpretability is important, the calculation (speed vs. team average) is relatively transparent. The critical issue isn't understanding the metric but the lack of human oversight in applying consequences
- Worker surveillance raises privacy concerns, but in employment contexts (especially US), employers generally have broad monitoring rights in the workplace. Privacy is a concern but less critical than automated termination without human review
- Algorithmic bias is a valid concern (workers with disabilities may work slower), but the immediate governance failure is the automated decision pipeline. Bias should be assessed, but the lack of human oversight affects all workers and is the more fundamental governance failure

</details>

---

