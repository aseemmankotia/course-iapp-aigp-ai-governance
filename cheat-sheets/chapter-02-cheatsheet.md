# AI Development Lifecycle & Documentation — Quick Reference

## Lifecycle Stages & Accountability

| Stage | Key Activities | Primary Accountability | Exit Criteria |
|-------|---------------|----------------------|---------------|
| 1. Problem Definition | Define use case, legal feasibility, success criteria, high-risk classification | AI governance + business owner | Use case approved, risks identified, metrics defined |
| 2. Data Collection | Gather data, assess representativeness, document provenance | Data engineers + domain experts | Datasheet complete, data quality validated |
| 3. Model Development | Train model, select architecture, feature engineering | Data scientists | Model meets performance targets on dev set |
| 4. Validation | Test on held-out data, fairness testing, bias analysis | Data scientists + validation team | Model card complete, passes fairness thresholds |
| 5. Deployment | Production release, integration, user training | MLOps + business unit | Monitoring active, runbook documented |
| 6. Monitoring | Performance tracking, drift detection, incident response | Business unit (model owner) | Ongoing — triggers return to earlier stages if degraded |

## Critical Documentation Artifacts

### Model Cards (Mitchell et al. 2019)
**Required sections:**
- Model details: version, type, training date, intended use
- Performance metrics: **disaggregated by protected characteristics**
- Limitations: known failure modes, out-of-scope use cases
- Training data: high-level description (detailed in datasheet)
- Ethical considerations: bias analysis, fairness metrics

**Exam trap:** Model cards show *model* performance; datasheets describe *dataset* composition. Don't confuse.

### Datasheets for Datasets (Gebru et al. 2018)
**Required sections:**
- Motivation: Why was dataset created?
- Composition: What's in it? Demographics? Size?
- Collection: How was data gathered? Who collected it?
- Preprocessing: Cleaning, filtering, transformations applied
- Distribution: How is dataset shared? License?
- Maintenance: Who maintains? Update frequency?

**Use case:** Assess data representativeness and provenance for bias risk.

### Fundamental Rights Impact Assessment (FRIA) — EU AI Act Article 27
**Mandatory for:** High-risk AI systems (Annex III: biometrics, employment, essential services, law enforcement, education, critical infrastructure)

**Must assess:**
- Impact on fundamental rights (health, privacy, non-discrimination, dignity)
- Affected groups and potential harms
- Mitigation measures
- Necessity and proportionality of system

**Timing:** BEFORE deployment

**Exam trap:** FRIA is legal requirement for high-risk AI, not best practice. Model cards are recommended but not legally mandated by EU AI Act.

## Performance Degradation & Drift

| Type | Definition | Indicator | Action Required |
|------|-----------|-----------|----------------|
| **Concept Drift** | Relationship between features and target changes | Accuracy drops for specific segment; feature importance shifts | **Retrain model** with new data reflecting new relationships |
| **Data Drift** | Input distribution changes but relationship same | Feature distributions shift from training data | Monitor; may need retraining if severe |
| **Performance Degradation** | Model predictions become less accurate/reliable | Overall or segmented accuracy/precision/recall drops | Investigate cause (drift, data quality, adversarial); likely retrain |

**Exam scenario:** If accuracy drops 16 points for one demographic group → likely concept drift → return to data collection/model development stages.

## Third-Party Model Procurement — Required Due Diligence

### Vendor Information Required:
1. Training data sources and representativeness (can they refuse? Yes, but creates procurement risk)
2. Performance metrics (disaggregated by demographics)
3. Model update/versioning policy and notification process
4. Known limitations and failure modes
5. Support and incident response SLAs

### Critical Contractual Clauses:
- **Indemnification:** Vendor liability for discriminatory/harmful AI outputs
- **Audit rights:** Right to review vendor's AI governance practices
- **Data processing terms:** GDPR/privacy compliance for any data shared with vendor
- **Liability allocation:** Who's responsible if model fails or causes harm?
- **Termination rights:** Exit provisions if performance degrades
- **Version control:** Notification before model updates that change behavior

**Exam trap:** SLAs cover uptime, not output quality. Indemnification transfers liability risk.

## High-Risk AI — EU AI Act Annex III Examples
- Biometric identification (facial recognition, emotion detection)
- Employment/HR (recruiting, promotion, termination, monitoring)
- Access to essential services (credit scoring, insurance underwriting)
- Law enforcement (predictive policing, risk assessment)
- Education (exam scoring, admission decisions)
- Critical infrastructure (energy grid management)

**Consequences:** Conformity assessment, CE marking, third-party audits, FRIA, extensive documentation, registration in EU database.

## Data Quality Requirements
**Representativeness:** Training data must match deployment population distribution across relevant characteristics (demographics, geography, contexts).

**Exam scenario:** Model performs well on test set from Region A but poorly on held-out data from Region B → non-representative training data → return to data collection stage.

**Volume:** Sufficient examples across all subgroups to avoid small sample bias.

**Labeling quality:** Inter-annotator agreement, label noise assessment.

**Temporal relevance:** Data reflects current conditions, not outdated patterns.

## Version Control Triggers
**Mandatory new version:**
- Model retraining
- Architecture changes
- Feature engineering modifications
- Hyperparameter changes affecting predictions
- Training data changes

**Purpose:** Auditability, rollback capability, change tracking for compliance.

**Exam tip:** Infrastructure changes (API endpoints, scaling) don't require model versioning; changes affecting predictions do.
