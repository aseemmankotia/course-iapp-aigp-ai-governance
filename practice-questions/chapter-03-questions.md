## Chapter 3: Responsible AI: Fairness, Bias, and Transparency — Practice Questions

**Q1.** A healthcare AI system for predicting patient readmission rates shows 92% accuracy for majority patients but only 78% accuracy for underrepresented ethnic groups. Historical hospital data shows the underrepresented groups had fewer follow-up appointments recorded. Which type of bias is PRIMARILY demonstrated, and what mitigation approach is most appropriate?

A) Measurement bias; apply post-processing calibration to adjust prediction thresholds per demographic group
B) Representation bias; collect additional training data from underrepresented groups and use oversampling techniques during training
C) Historical bias; use pre-processing techniques to remove protected attributes from the dataset entirely
D) Aggregation bias; deploy separate models for each demographic group with independent training pipelines

<details>
<summary>Answer</summary>

**Correct: B**

This is representation bias (undersampling) because underrepresented groups have fewer data points in training set. The solution is in-processing mitigation: collect more data from underrepresented groups and use oversampling (SMOTE, etc.) during training to balance the dataset. This directly addresses the root cause.

**Why the others are wrong:**
- This describes post-processing mitigation for a different problem. Measurement bias occurs when the proxy variable (follow-up appointments) doesn't accurately measure the target (readmission risk), but the primary issue here is insufficient data representation, not proxy measurement error.
- Removing protected attributes (fairness through unawareness) doesn't fix representation bias and can worsen fairness because the model can't account for legitimate group differences. This is a discredited pre-processing approach.
- Separate models per group (disaggregation) addresses aggregation bias where one model poorly fits heterogeneous groups. However, with insufficient training data for underrepresented groups, separate models would perform even worse due to data scarcity.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** Under GDPR Article 22, an EU citizen contests an automated credit denial decision. The lender provides a detailed SHAP value explanation showing which features contributed most to the denial. Does this satisfy the 'right to explanation' requirement?

A) Yes, SHAP values constitute meaningful information about the logic involved as required by Article 22(1)
B) No, Article 22 requires human review of solely automated decisions with legal/significant effects, not just explanations
C) Yes, but only if the SHAP explanation includes counterfactual examples showing how to achieve approval
D) No, GDPR Article 22 has been superseded by EU AI Act Article 13 transparency requirements which mandate different explanation formats

<details>
<summary>Answer</summary>

**Correct: B**

GDPR Article 22 grants the right NOT to be subject to solely automated decisions with legal/significant effects. The requirement is human intervention/review, not explanation. Article 13-15 require information about logic, but Article 22 requires meaningful human oversight. Providing SHAP values without human review doesn't satisfy Article 22.

**Why the others are wrong:**
- GDPR Articles 13-15 require 'meaningful information about the logic involved' but this is separate from Article 22's right to human intervention. SHAP values alone don't satisfy the Article 22 requirement for non-automated decision-making.
- Counterfactual explanations enhance transparency but don't change the fact that Article 22 requires human review for solely automated decisions with significant effects, not enhanced explanations.
- EU AI Act complements but doesn't supersede GDPR Article 22. Article 22 remains in force. EU AI Act Article 13 adds transparency obligations for high-risk systems but doesn't replace Article 22's human review requirement.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A company deploys an AI hiring system classified as high-risk under EU AI Act. Which human oversight model satisfies Article 14 requirements for this system?

A) Human-on-the-loop: humans monitor system performance metrics and can intervene if aggregate fairness metrics fall below thresholds
B) Human-in-command: humans can decide when and how to use the system but don't review individual decisions
C) Human-in-the-loop: humans review and approve every AI recommendation before any hiring decision is made
D) Automated oversight: AI monitoring system flags anomalous decisions for periodic human audit

<details>
<summary>Answer</summary>

**Correct: C**

EU AI Act Article 14 requires human oversight for high-risk AI systems including employment decisions. Human-in-the-loop is the strongest model where humans review and can override every decision before action is taken. For high-risk hiring decisions affecting fundamental rights, individual decision review (not just aggregate monitoring) is required.

**Why the others are wrong:**
- Human-on-the-loop allows monitoring and intervention but doesn't require review of individual decisions before they take effect. For high-risk systems affecting employment (fundamental rights), Article 14 requires more active oversight than passive monitoring.
- Human-in-command means humans control when to use the system but can still make solely automated decisions once deployed. This doesn't satisfy Article 14's requirement for oversight of the AI system's individual outputs in high-risk scenarios.
- Automated oversight with periodic audit doesn't provide meaningful human oversight as required by Article 14. The oversight must be by natural persons who can understand outputs and intervene, not another AI system.

</details>

---

**Q4.** An AI system achieves 95% demographic parity (equal positive prediction rates across groups) but shows significant disparity in false positive rates: 5% for Group A vs 18% for Group B. The system is used for loan approvals. Which fairness metric is violated and what is the business impact?

A) Individual fairness is violated; similar individuals are treated differently regardless of group membership
B) Equalized odds is violated; Group B faces higher rate of incorrect denials, creating discriminatory impact even with equal approval rates
C) Predictive parity is violated; the positive predictive value differs between groups, affecting loan default rates
D) Calibration fairness is violated; predicted probabilities don't match actual outcomes equally across groups

<details>
<summary>Answer</summary>

**Correct: B**

Equalized odds requires equal true positive rates AND equal false positive rates across groups. False positive rate disparity (18% vs 5%) violates equalized odds. For loans, this means Group B qualified applicants are incorrectly denied at 3.6x the rate of Group A qualified applicants—clear discriminatory impact despite demographic parity.

**Why the others are wrong:**
- Individual fairness (similar individuals treated similarly) may be violated but the question describes group-level disparities in false positive rates, which is specifically an equalized odds violation. Individual fairness is harder to measure and test.
- Predictive parity (equal PPV across groups) concerns whether approved applicants from different groups have equal default rates. The question describes false positive rates (qualified applicants incorrectly denied), not prediction accuracy for approved loans.
- Calibration fairness requires predicted probabilities match actual outcomes within groups. While related, the specific metric violated here is equalized odds (equal error rates). Calibration could be satisfied even with different false positive rates if probabilities are correctly calibrated within each group.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A financial services company must explain AI-driven trading decisions to regulators. They consider LIME vs SHAP explanations. Which statement about these methods is correct?

A) LIME provides global explanations of overall model behavior; SHAP provides local explanations for individual predictions
B) SHAP values satisfy the consistency property (if model changes to rely more on a feature, SHAP value doesn't decrease); LIME approximations don't guarantee this
C) LIME is model-agnostic and works with any black-box model; SHAP requires access to model internals and gradients
D) SHAP is computationally cheaper for high-dimensional data; LIME requires exponential computation time as features increase

<details>
<summary>Answer</summary>

**Correct: B**

SHAP (SHapley Additive exPlanations) values are based on game theory and satisfy consistency: if a model changes to rely more on feature X, SHAP value for X cannot decrease. LIME (Local Interpretable Model-agnostic Explanations) uses local linear approximations which don't guarantee this mathematical property. This is a key theoretical distinction.

**Why the others are wrong:**
- Reversed: LIME provides LOCAL explanations (trains simple model on perturbed instances near a single prediction). SHAP can provide both local (individual Shapley values) and global (average absolute SHAP values) explanations.
- Both LIME and SHAP are model-agnostic in principle. While some SHAP variants (GradientSHAP) use gradients for efficiency, basic SHAP (KernelSHAP) works with any black-box model just like LIME. Neither requires model internals access.
- Reversed: SHAP exact computation can be exponential (2^n for n features). LIME is typically faster because it approximates with a simple linear model on perturbed samples. TreeSHAP is efficient for tree models, but general SHAP is computationally expensive.

</details>

---

**Q6.** A healthcare AI company wants to train a diagnostic model on patient data from 50 hospitals while preserving privacy. Each hospital cannot share raw patient data due to regulations. Which privacy-enhancing technology is MOST appropriate?

A) Differential privacy: add calibrated noise to each hospital's dataset before aggregating centrally for training
B) Federated learning: train local models at each hospital and aggregate only model updates centrally without sharing patient data
C) Synthetic data: generate artificial patient records at each hospital using GANs and pool synthetic data centrally
D) Homomorphic encryption: encrypt all patient data and perform training computations on encrypted data centrally

<details>
<summary>Answer</summary>

**Correct: B**

Federated learning is designed exactly for this scenario: train models locally at each hospital on their private data, send only model updates (gradients/weights) to central server, aggregate updates without seeing raw data. This satisfies 'cannot share raw patient data' requirement while enabling collaborative training across 50 institutions.

**Why the others are wrong:**
- Differential privacy adds privacy guarantees but still requires aggregating datasets centrally (even if noised). The constraint is that hospitals 'cannot share patient data'—even noised data may violate this. DP is typically applied to query outputs or model updates, not as a primary data sharing mechanism.
- Synthetic data generation requires sophisticated techniques and validation that synthetic data preserves clinical utility while removing identifiability. GAN-generated data at scale across 50 hospitals introduces consistency and quality challenges. Federated learning is more established for this multi-party scenario.
- Homomorphic encryption allows computation on encrypted data but is computationally expensive (orders of magnitude slower) and impractical for training deep learning models at scale across 50 institutions. Current homomorphic encryption cannot efficiently handle neural network training.

</details>

---

**Q7.** An insurance company's AI model uses zip code as a feature. Zip code correlates strongly with race (protected attribute). Regulators claim this violates fairness through the use of a proxy variable. Which type of bias does this represent, and what is the correct mitigation approach?

A) Historical bias; use pre-processing to remove zip code and all correlated features from training data
B) Measurement bias; zip code is a proxy for socioeconomic factors, not race—mitigation requires collecting direct socioeconomic features instead
C) Representation bias; certain zip codes are underrepresented in training data—mitigation requires oversampling minority zip codes
D) Aggregation bias; one model doesn't fit all zip codes—mitigation requires training separate models per geographic region

<details>
<summary>Answer</summary>

**Correct: B**

This is measurement bias: zip code is used as a proxy variable for actual risk factors (socioeconomic status, access to healthcare, etc.) but inadvertently proxies for race due to residential segregation. Correct mitigation: measure the actual underlying factors directly rather than using problematic proxies. This improves both fairness and model quality.

**Why the others are wrong:**
- While removing correlated features is a pre-processing technique, simply removing zip code without addressing what it proxies for doesn't solve the problem—other features may still encode similar information (redlining). The solution is measuring actual risk factors, not feature removal.
- The scenario doesn't indicate undersampling of certain zip codes, but rather that zip code itself is a problematic proxy. Oversampling minority zip codes doesn't address the fundamental issue that zip code shouldn't be used as a proxy for race in insurance pricing.
- Aggregation bias occurs when one model poorly fits heterogeneous subgroups. The issue here isn't model fit across geographies but that zip code proxies for a protected attribute. Geographic models might worsen fairness by institutionalizing zip code-based discrimination.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** A company implements differential privacy with ε=0.1 vs ε=10 for their AI training data. What is the privacy-utility trade-off between these settings?

A) ε=0.1 provides stronger privacy (less information leakage) but lower model utility due to more noise; ε=10 provides weaker privacy but higher utility
B) ε=10 provides stronger privacy protection with tighter privacy budget; ε=0.1 allows more queries with weaker privacy
C) Both provide equivalent privacy; ε only affects computational efficiency of the privacy mechanism
D) ε=0.1 provides privacy for 10% of individuals; ε=10 provides privacy for 100% of individuals in the dataset

<details>
<summary>Answer</summary>

**Correct: A**

In differential privacy, epsilon (ε) represents the privacy budget: LOWER ε = STRONGER privacy (less distinguishability between datasets differing by one individual) but requires MORE noise, reducing utility. ε=0.1 adds significant noise for strong privacy. ε=10 is weak privacy (nearly distinguishable) with little noise, preserving utility. This is the fundamental privacy-utility trade-off.

**Why the others are wrong:**
- Reversed: Lower ε = stronger privacy (tighter privacy budget). ε=10 is considered weak privacy in differential privacy literature. The privacy budget is like a spending limit—smaller budget (ε=0.1) means less 'spending' of privacy.
- ε directly affects privacy guarantees, not computational efficiency. The privacy-utility trade-off is fundamental to differential privacy—ε controls how much the output can differ between neighboring datasets, which requires calibrated noise addition.
- ε doesn't represent percentage of protected individuals. Differential privacy protects all individuals in the dataset by bounding the privacy loss from any individual's data. ε quantifies the maximum privacy loss (information leakage) for any individual.

</details>

---

