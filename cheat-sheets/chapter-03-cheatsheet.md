# Responsible AI: Fairness, Bias, Transparency — Exam Cheat Sheet

## Bias Types (Heavily Tested)

| Bias Type | Definition | Example | Mitigation |
|-----------|------------|---------|------------|
| **Historical** | Training data reflects past discrimination | Hiring data shows historical gender bias in promotions | Pre-processing: reweight samples, remove biased labels |
| **Representation** | Undersampling of groups in training data | 90% majority, 10% minority examples | In-processing: oversample minority class (SMOTE), class weights |
| **Measurement** | Proxy variables don't measure target accurately | Zip code proxies socioeconomic status but encodes race | Pre-processing: collect direct measurements, remove proxies |
| **Aggregation** | One model poorly fits heterogeneous groups | Single model for diverse patient populations | Post-processing: disaggregated models or group-specific thresholds |

## Fairness Metrics (Know Trade-offs)

| Metric | Definition | What it Requires | When Violated |
|--------|------------|------------------|---------------|
| **Demographic Parity** | Equal positive prediction rates across groups | P(Ŷ=1\|A=a) = P(Ŷ=1\|A=b) | Different approval rates by group |
| **Equalized Odds** | Equal TPR and FPR across groups | P(Ŷ=1\|Y=y,A=a) = P(Ŷ=1\|Y=y,A=b) | Different error rates by group |
| **Individual Fairness** | Similar individuals treated similarly | d(x₁,x₂) small → d(f(x₁),f(x₂)) small | Similar people get different outcomes |

**Exam Note**: Cannot satisfy all fairness metrics simultaneously (impossibility theorem). Demographic parity ignores accuracy, equalized odds is stricter.

## Mitigation Techniques (Pipeline Position)

**Pre-processing** (before training):
- Reweighting samples
- Resampling (over/under-sampling)
- Removing protected attributes (often ineffective—proxies remain)

**In-processing** (during training):
- Fairness constraints in loss function
- Adversarial debiasing
- Prejudice remover regularizer

**Post-processing** (after training):
- Threshold optimization per group
- Calibration adjustment
- Reject option classification

## Explainability Methods (Know Use Cases)

| Method | Type | What It Shows | Best For |
|--------|------|---------------|----------|
| **SHAP** | Local + Global | Feature contribution (Shapley values) | Tabular data, consistency property needed |
| **LIME** | Local | Local linear approximation | Black-box models, fast approximation |
| **Counterfactuals** | Local | Minimal changes to flip decision | Actionable recourse |
| **Saliency Maps** | Local | Important input regions (gradients) | Images, text |

**Key Distinctions**:
- **Explainability**: How model produces outputs (mechanism)
- **Interpretability**: Degree to which human can understand model
- **Transparency**: Openness about model design, data, limitations

## Privacy-Enhancing Technologies

| Technology | How It Works | Privacy Level | Use Case |
|------------|--------------|---------------|----------|
| **Differential Privacy** | Add calibrated noise (ε parameter) | ε=0.1 strong, ε=10 weak | Query outputs, model updates |
| **Federated Learning** | Decentralized training, share model updates only | Moderate (vulnerable to inference) | Multi-party data, no central data pool |
| **Synthetic Data** | Generate artificial data (GANs, etc.) | Varies (can leak info) | Data sharing, testing |
| **Homomorphic Encryption** | Compute on encrypted data | Strong (computationally expensive) | Outsourced computation |

**Differential Privacy**: Lower ε = more privacy, less utility. Privacy budget.

## Regulatory Requirements (Exam Loves These)

### GDPR Article 22
- Right NOT to be subject to solely automated decisions with legal/significant effects
- Requires: **Human intervention** (not just explanation)
- Articles 13-15: Require information about logic, but separate from Article 22

### EU AI Act Article 14 (Human Oversight)
For high-risk systems:
- **Human-in-the-loop**: Review/approve each decision (required for high-risk)
- **Human-on-the-loop**: Monitor, can intervene (insufficient for high-risk)
- **Human-in-command**: Control when to use system (insufficient for high-risk)

**Exam Trap**: Article 22 = human review requirement, NOT explanation requirement.

## Common Exam Traps

1. **Fairness through unawareness**: Removing protected attributes ≠ fairness (proxies remain)
2. **Demographic parity vs equalized odds**: DP only requires equal outcomes, EO requires equal error rates
3. **LIME provides global explanations**: FALSE—LIME is local only, SHAP does both
4. **Synthetic data is automatically private**: FALSE—GANs can memorize training data
5. **Higher epsilon = more privacy**: FALSE—lower ε = stronger privacy
6. **GDPR Article 22 requires explanations**: FALSE—requires human intervention
7. **Human-on-the-loop sufficient for high-risk AI**: FALSE—requires human-in-the-loop
