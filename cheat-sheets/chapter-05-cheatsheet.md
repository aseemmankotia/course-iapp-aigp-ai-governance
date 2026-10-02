# NIST AI RMF Quick Reference

## Four Core Functions

| Function | Purpose | Key Activities | Exam Note |
|----------|---------|----------------|------------|
| **GOVERN** | Overarching, continuous function | Policies, roles, culture, oversight structures | NOT just first step—runs throughout lifecycle |
| **MAP** | Understand context & risks | Context, categorization, risk mapping across lifecycle | Categorization = ALL 7 trustworthy characteristics |
| **MEASURE** | Establish metrics | Metrics & benchmarks for trustworthy characteristics | Measure ALL 7 characteristics, emphasize high-risk |
| **MANAGE** | Respond to risks | Risk response, continuous improvement, incident response | 'Manage' ≠ 'eliminate'—ongoing mitigation |

## Seven Trustworthy Characteristics

1. **Valid and Reliable** - Consistent, accurate performance
2. **Safe** - No unacceptable harm under expected use
3. **Secure and Resilient** - Protected from threats, recovers from disruptions
4. **Accountable and Transparent** - Clear responsibility, disclosed information
5. **Explainable and Interpretable** - Understandable decisions and logic
6. **Privacy-Enhanced** - PII protected, data minimization
7. **Fair with Harmful Bias Managed** - Ongoing bias mitigation (not elimination)

**Exam trap**: Explainability (communication) ≠ Interpretability (technical understanding)

## NIST vs EU AI Act: Critical Differences

| Aspect | NIST AI RMF | EU AI Act |
|--------|-------------|------------|
| **Legal Status** | Voluntary framework | Legally binding regulation |
| **Risk Tiering** | Context-dependent, no preset tiers | Fixed categories by use case |
| **Risk Categories** | Assessed per implementation | Unacceptable/High/Limited/Minimal |
| **Approach** | Flexible, map to other frameworks | Prescriptive requirements |
| **Geography** | International (despite US origin) | EU jurisdiction |

**Exam focus**: NIST has NO predefined risk levels—this is heavily tested

## Function Relationships

```
GOVERN (continuous, overarching)
    ↓
    Enables all functions
    ↓
MAP → MEASURE → MANAGE (sequential but iterative)
    ↑________________↓
    Feedback loop for continuous improvement
```

## MEASURE Function Requirements

**Must measure**:
- ALL seven trustworthy characteristics (not just high-risk)
- Technical performance (accuracy, precision, recall, etc.)
- Trustworthy characteristic metrics (fairness metrics, privacy metrics, etc.)
- Benchmarks for comparison

**Exam trap**: Cannot measure only high-risk characteristics—need baseline for all

## MANAGE Function: Risk Response Options

1. **Treat** - Implement controls to reduce risk
2. **Accept** - Acknowledge and document risk
3. **Transfer** - Share risk (insurance, contracts)
4. **Avoid** - Eliminate activity causing risk

**Incident Response**: Document → Assess severity → Respond → Communicate → Monitor

## Crosswalks (Framework Mapping)

**Available crosswalks**:
- ISO/IEC 42001 (AI Management System)
- EU AI Act
- OECD AI Principles
- Other national/international frameworks

**Purpose**: Map NIST controls to other framework requirements without duplicate governance

**Exam note**: Crosswalk is core NIST feature—enables multi-framework compliance

## NIST AI RMF Playbook

- Provides **suggested** actions (not mandatory)
- Implementation guidance for each function
- Must be **customized** to organizational context
- Examples and considerations, not prescriptive steps

**Exam trap**: Playbook ≠ requirements—it's guidance

## Common Exam Traps

1. **GOVERN as first step only** → It's continuous, overarching
2. **Measure only high-risk characteristics** → Must measure all 7
3. **Explainability = Interpretability** → Different concepts
4. **NIST has risk tiers like EU** → NIST is context-dependent, no preset tiers
5. **Bias must be eliminated** → 'Managed' not 'eliminated'
6. **NIST is US-only** → Designed for international use
7. **Playbook = requirements** → Playbook = suggestions
8. **Crosswalks require new framework** → Map existing controls

## MAP Function Sequence

1. **Context** - Purpose, stakeholders, environment, constraints
2. **Categorization** - Impact across all 7 trustworthy characteristics
3. **Risk Mapping** - Risks across AI lifecycle stages (design, development, deployment, monitoring)

**Next step after MAP**: MEASURE (not MANAGE)

## Quick Decision Trees

**When to use NIST AI RMF**:
- ✅ Need flexible, voluntary framework
- ✅ Multi-jurisdiction compliance (use crosswalks)
- ✅ Want to map to other frameworks
- ✅ Need comprehensive risk management approach

**NIST AI RMF is NOT**:
- ❌ Legally binding regulation
- ❌ Certification program
- ❌ Prescriptive checklist
- ❌ Replacement for domain-specific regulations
