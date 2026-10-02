# ISO/IEC 42001 & AI Governance Quick Reference

## ISO/IEC 42001 Clause Structure (Exam Tested Order)
| Clause | Focus | Key Exam Points |
|--------|-------|----------------|
| **4: Context** | Organization & stakeholders | Understand context AND determine interested parties' needs BEFORE policy |
| **5: Leadership** | AI policy, roles | Policy must commit to continual improvement (mandatory for cert) |
| **6: Planning** | Objectives, risk assessment | AI-specific risks (bias, fairness) beyond general enterprise risk |
| **7: Support** | Resources, competence | Not heavily tested — competence requirements for AI roles |
| **8: Operation** | Lifecycle controls, Annex A | Where Annex A controls are implemented; inventory maintained here |
| **9: Performance** | Monitoring, audit, review | Need ongoing evidence: dashboards, review minutes, audit reports |
| **10: Improvement** | Nonconformity, continual improvement | Links back to Clause 5 policy commitment |

## AI System Inventory — Mandatory Fields
| Field | Purpose | Exam Gotcha |
|-------|---------|-------------|
| **System ID** | Unique identifier | Must be trackable across lifecycle |
| **Use Case** | Business purpose | Determines risk context |
| **Risk Tier** | High/Medium/Low | Determines control depth (proportionate) |
| **Data Sources** | Input data origins | Critical for bias/quality assessment |
| **Accountability** | Who decides/owns outcomes | "Owner" ≠ accountability; must specify decision authority |

## AI Risk Assessment: AI-Specific vs. General Enterprise
| Risk Type | AI-Specific | General Enterprise |
|-----------|-------------|-------------------|
| **Focus** | Algorithmic bias, fairness, explainability, data quality → model behavior | Financial, operational, cyber, compliance |
| **Example** | Recommendation system discriminates by race/gender | Recommendation system causes revenue loss |
| **Methodology** | Must assess training data bias, protected characteristics, disparate impact | Standard risk matrix (likelihood × impact) |
| **Exam Trap** | If question asks "AI risk assessment," choose bias/fairness answer over cost/security |

## Conformity Assessment Types
| Type | Who Performs | When Required | Certification? |
|------|--------------|---------------|---------------|
| **Third-party audit** | Accredited certification body | For ISO/IEC 42001 certification | YES |
| **Self-assessment** | Internal team | Ongoing internal monitoring | NO |
| **Notified body** | EU-designated authority | EU AI Act high-risk systems | YES (for EU compliance) |
| **Exam Tip** | High-risk AI in EU: notified body review + can leverage ISO cert for governance portions |

## ISO/IEC 42001 Policy Requirements (Clause 5.2)
✅ MUST include:
- Commitment to **continual improvement** (non-negotiable)
- Commitment to comply with requirements
- Framework for setting AI objectives

❌ Common mistakes:
- Vague commitments ("ethical AI") without continual improvement
- Listing specific risks instead of management system commitments
- Confusing policy with procedures/controls

## Annex A Controls — What They Are
- **Catalog** of AI-specific controls across lifecycle
- **Selected** based on Clause 6 risk assessment
- **Implemented** in Clause 8 operations
- **Cover**: data governance, model dev, deployment, monitoring, impact assessment, human oversight
- **Exam trap**: Annex A controls are applied *proportionately* based on risk tier

## Proportionate Governance Principle
| Risk Tier | Inventory? | Control Depth | Documentation |
|-----------|-----------|---------------|---------------|
| **High** | ✅ Required | Full Annex A controls | Extensive risk assessment, control evidence |
| **Low** | ✅ Required | Basic controls | Core inventory fields, lighter documentation |
| **Exam Gotcha** | ALL systems in inventory with core fields; proportionality = control depth, not whether governed |

## Performance Evaluation Evidence (Clause 9)
Auditors look for:
1. **Monitoring**: Dashboards, metrics, KPIs (ongoing, not one-time)
2. **Internal audit**: Audit plans, reports, findings, corrective actions
3. **Management review**: Meeting minutes, decisions, resource allocation

❌ NOT performance evaluation:
- Initial setup docs (policy, org chart)
- Inventory/control records (those are Clause 8)
- Training certificates (those are Clause 7)

## EU AI Act Integration
- **Harmonized standard**: ISO/IEC 42001 creates presumption of conformity for governance aspects
- **High-risk systems**: Still need notified body for EU-specific requirements
- **Strategy**: Get ISO cert first, then notified body review for EU gaps
- **Exam tip**: ISO/IEC 42001 ≠ complete EU AI Act compliance, but reduces burden

## Numbers to Remember
- **Published**: 2023 (first certifiable AI mgmt standard)
- **Clauses tested**: 4, 5, 6, 8, 9 (context, leadership, planning, operations, evaluation)
- **Inventory fields**: 5 mandatory minimum (ID, use case, risk tier, data, accountability)
- **Assessment types**: 3 (self, third-party, notified body)
