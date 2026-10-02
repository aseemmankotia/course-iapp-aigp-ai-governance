# EU AI Act Part 2: High-Risk Compliance & Global AI Laws

## High-Risk AI Requirements (Articles 8-15)

| Article | Requirement | Key Obligations |
|---------|-------------|----------------|
| **Art 9** | Risk Management | Continuous, iterative process; identify/estimate/evaluate risks; adopt mitigation; test system |
| **Art 10** | Data Governance | Examine datasets for biases; identify gaps; ensure relevance, representativeness, completeness |
| **Art 11** | Technical Documentation | Demonstrate compliance; keep updated; include system description, design, data, risk management |
| **Art 12** | Record-Keeping/Logs | Automatically generated; enable traceability; appropriate retention period; secure storage |
| **Art 13** | Transparency to Deployers | Provide: intended purpose, accuracy level, limitations, foreseeable misuse |
| **Art 14** | Human Oversight | Enable humans to understand, monitor, intervene; stop button/halt function required |
| **Art 15** | Accuracy/Robustness/Cybersecurity | Appropriate levels throughout lifecycle; resilient to errors, third-party attacks |

## Conformity Assessment Procedures

| Type | Annex | Who Assesses | When Required | CE Marking |
|------|-------|--------------|---------------|------------|
| **Internal** | Annex VI | Provider self-assesses | Most high-risk AI systems | Yes, self-issue after assessment |
| **Third-Party** | Annex VII | Notified body | Biometric identification, critical infrastructure | Yes, after notified body approval |

**Declaration of Conformity Requirements:**
- Technical documentation file
- Post-market monitoring plan
- Quality management system documentation
- CE marking affixed to product/packaging

## GDPR and EU AI Act Intersection

| GDPR Provision | AI Context | EU AI Act Link | Combined Requirement |
|----------------|------------|----------------|---------------------|
| **Art 22** | Automated decisions | Art 14 (human oversight) | Meaningful info on logic + human intervention capability |
| **Art 35** | DPIA | High-risk AI processing | DPIA mandatory for high-risk AI with personal data |
| **Art 6(1)(f)** | Legitimate interest | Art 10 (data governance) | LIA required; balance innovation vs rights; implement safeguards |
| **Art 36** | Prior consultation | High residual risks | Consult authority if DPIA shows unmitigated high risk |

**Legal Bases for AI Training Data:**
- Most common: Legitimate interest (6(1)(f))—requires LIA, balancing test
- Rarely practical: Consent (6(1)(a))—impractical for large-scale scraping
- Not applicable: Contract (6(1)(b))—no contract with scraped subjects

## US AI Landscape (2026)

**Federal Level:**
- No comprehensive federal AI law enacted
- Executive Order 14110 (Oct 2023): foundation models >10^26 ops must share safety tests with gov't
- FTC enforcement: uses Section 5 (unfair/deceptive practices)
- NIST AI RMF: 4 functions—Govern, Map, Measure, Manage

**State Laws:**

| State | Law | Effective | Key Requirements |
|-------|-----|-----------|------------------|
| **Colorado** | AI Act | Feb 2026 | Impact assessments for high-risk AI; notice to consumers; opt-out for consequential decisions |
| **California** | AB 2013 | Varies | Transparency for automated decision tools |
| **NYC** | Local Law 144 | 2023 | Annual bias audit + publish results; notify candidates about AI hiring tools |

## Other Key Jurisdictions

| Country | Framework | Status | Key Feature |
|---------|-----------|--------|-------------|
| **Canada** | AIDA (Artificial Intelligence and Data Act) | Proposed | Risk-based approach; penalties for high-impact systems |
| **China** | Various regulations | Active | Algorithmic recommendation rules; deep synthesis regs; generative AI rules |
| **Singapore** | Model AI Governance Framework | Voluntary | Self-assessment, transparency, human oversight principles |
| **Brazil** | AI Bill | Under consideration | Rights-based approach similar to LGPD structure |

## Exam Quick-Check Numbers

- **Annex VII trigger:** Biometric ID + critical infrastructure only
- **Article 12 retention:** "Appropriate period" (context-dependent, no fixed time)
- **EO 14110 threshold:** 10^26 integer/floating-point operations
- **NYC LL144 audits:** Annual frequency required
- **NIST AI RMF functions:** 4 (Govern/Map/Measure/Manage)—Monitor NOT a core function

## Common Exam Traps

✗ Assuming all high-risk AI needs third-party notified body (only Annex VII categories)
✗ Thinking GDPR Article 22 allows fully automated decisions if accurate (always need human oversight)
✗ Believing 10-year log retention is required (must be appropriate to purpose, respect GDPR limits)
✗ Assuming consent is the only legal basis for AI training (legitimate interest most common)
✗ Confusing transparency to deployers (Art 13) with transparency to end-users (different obligations)
