# Chapter 7: AI Incident Response, Audit, and Assurance - Quick Reference

## AI Incident Categories (Know All 4)
| Category | Examples | Detection Method |
|----------|----------|------------------|
| **Discriminatory Outcomes** | Biased hiring, loan denials, unfair content moderation | Fairness monitoring, user complaints |
| **Privacy Breaches** | Model inversion, training data leakage, re-identification | Security monitoring, regulatory inquiry |
| **Safety Failures** | Autonomous vehicle crashes, medical misdiagnosis, physical harm | Incident reports, media coverage |
| **Adversarial Attacks** | Prompt injection, evasion attacks, data poisoning | Monitoring alerts, security testing |

## Incident Response Workflow (Memorize Order)
1. **CONTAIN** - Stop harm immediately (disable system, rollback, manual override)
2. **INVESTIGATE** - Root cause analysis (see below)
3. **REMEDIATE** - Fix the issue (retrain, patch, redeploy)
4. **DOCUMENT** - Record findings, decisions, timeline
5. **REPORT** - Notify regulators/users if required

**Exam Trap:** Never skip containment to investigate faster!

## Root Cause Analysis - 5 Categories
| Root Cause | Investigation Focus | Remediation |
|------------|-------------------|-------------|
| **Data Issues** | Training data quality, bias, coverage gaps | Data collection, labeling, augmentation |
| **Model Drift** | Production vs training distribution | Retraining, monitoring thresholds |
| **Adversarial Input** | Attack patterns, input validation gaps | Input sanitization, adversarial training |
| **Deployment Error** | Version mismatch, config errors, environment | Change management, testing, rollback |
| **Human Oversight Failure** | Policy gaps, approval bypasses, ignored alerts | Process improvement, training, automation |

## Incident Detection Methods
- **Monitoring Alerts** (proactive): Automated detection, best case
- **User Complaints** (reactive): External reporting, already causing harm
- **Regulatory Inquiry** (reactive): Authority investigation, serious
- **Media Reports** (reactive): Public awareness, reputational damage

**Exam Tip:** Proactive detection (monitoring) is always preferred over reactive.

## AI Audit Types (3 Main Categories)
| Audit Type | Scope | Performed By | Deliverable |
|------------|-------|--------------|-------------|
| **Algorithmic Audit** | Model fairness, accuracy, robustness testing | Internal or third-party | Fairness report, accuracy metrics |
| **Process Audit** | Governance policy compliance, oversight function | Internal or third-party | Compliance report, gap analysis |
| **Conformity Assessment** | Regulatory compliance (EU AI Act, etc.) | Third-party (required) | Certification, compliance attestation |

**Exam Note:** Third-party audits required for high-risk AI systems.

## Post-Incident Actions (Always Required)
1. **Model Retraining** - With improvements addressing root cause
2. **Policy Updates** - Prevent recurrence, update procedures
3. **Affected Party Notification** - If harm occurred (legally required for privacy)
4. **Governance Review** - Identify process failures, update controls

## Audit Documentation Requirements
**Must Preserve for Regulatory Inquiries:**
- Model training logs (datasets, hyperparameters, results)
- Inference logs (predictions for specific incidents)
- Model version metadata (what was deployed when)
- Change management records (who approved what changes)
- Governance meeting minutes (oversight committee records)
- Previous audit reports (pattern of issues)

**Exam Trap:** Technical logs prove what happened; process docs prove governance existed.

## Key Comparisons for Exam

**Internal vs Third-Party Audits:**
- Internal: Regular monitoring, less credible, company staff
- Third-party: Compliance required, independent, higher credibility

**Model Drift vs Model Decay:**
- Drift: Data distribution changed (external cause)
- Decay: Model deteriorated (internal cause)

**Containment vs Remediation:**
- Containment: STOP harm (immediate, temporary)
- Remediation: FIX cause (permanent solution)

## Common Exam Scenarios
1. **Discriminatory hiring AI** → Contain (disable), investigate (fairness audit), remediate (retrain with balanced data), notify (affected applicants)
2. **Privacy breach via model inversion** → Contain (disable inference API), investigate (attack vector), remediate (differential privacy), notify (affected users + regulator)
3. **Safety failure in autonomous system** → Contain (manual override), investigate (incident logs), remediate (model update + testing), document (for regulatory inquiry)

## Numbers to Memorize
- **Fairness thresholds**: Often 5-10% accuracy difference triggers investigation
- **Notification timing**: Privacy breach = 72 hours to regulator (GDPR)
- **Audit frequency**: High-risk systems = annual third-party audit typical

**Final Exam Tip:** Questions will describe incident → ask for first step (always CONTAIN) OR root cause (match to 5 categories) OR required actions (post-incident 3). Know the workflows cold!
