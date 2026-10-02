# AIGP Exam Strategy Cheat Sheet

## Exam Format & Timing
| Metric | Value | Strategy Implication |
|--------|-------|----------------------|
| Total questions | 100 | All worth same points—don't over-invest in any one question |
| Total time | 150 minutes | 90 seconds per question average |
| Passing score | ~70% (estimated) | You can miss ~30 questions and still pass |
| Question types | 60% scenario, 30% knowledge, 10% comparison | Focus on applying concepts to scenarios |

## Domain Distribution & Time Allocation
| Domain | Questions | Time Budget (90 sec avg) | Strategy |
|--------|-----------|--------------------------|----------|
| Domain 5: Laws | ~27 (27%) | ~40 minutes | Memorize article numbers; flag hard article-recall questions |
| Domain 4: Risk/Governance | ~25 (25%) | ~37 minutes | Know framework structures (NIST functions, ISO sections) |
| Domain 3: Responsible AI | ~20 (20%) | ~30 minutes | Scenario-based bias identification; protected characteristics |
| Domain 2: Lifecycle | ~15 (15%) | ~22 minutes | Artifact requirements (documentation, testing, validation) |
| Domain 1: Foundations | ~13 (13%) | ~19 minutes | Actor roles (provider, deployer, controller, processor) |

## Flag-and-Return Strategy
**When to flag:** Any question taking >2 minutes (exceeds 90-second average)  
**When to return:** After completing all unflagged questions  
**Priority on return:** Easiest flagged questions first (quick wins), then harder questions with remaining time

## Time Management Checkpoints
| Checkpoint | Target Time | If Behind Pace |
|------------|-------------|----------------|
| 25 questions | 37.5 minutes | Flag next 2-3 hard questions |
| 50 questions | 75 minutes | Increase flagging threshold to >90 seconds |
| 75 questions | 112.5 minutes | Flag all Domain 4/5 questions taking >90 seconds |
| 90 questions | 135 minutes | Answer all remaining, guess on flagged if <2 min left |

## Scenario Question Strategy (60% of exam)
**Step 1:** Identify the key constraint (first 1-2 sentences)  
- Jurisdiction (EU, US, China)  
- Risk tier (prohibited, high-risk, limited-risk, minimal-risk)  
- Lifecycle stage (design, development, deployment, monitoring)  
- Actor role (provider, deployer, controller, processor)  

**Step 2:** Identify what's being asked  
- Compliance requirement (which law/article?)  
- Risk mitigation (which control?)  
- Governance decision (which framework function?)  

**Step 3:** Eliminate wrong answers by finding the flaw  
- Too broad (covers more than scenario requires)  
- Too narrow (misses a key requirement from scenario)  
- Wrong jurisdiction (applies EU law to US scenario)  
- Wrong risk tier (treats high-risk as prohibited)  
- Wrong lifecycle stage (deployment obligation applied to design)  

## Common Exam Traps
| Trap | What Students Confuse | How to Avoid |
|------|----------------------|-------------|
| Provider vs Deployer | Who has which obligations | Provider = develops/supplies; Deployer = puts into service |
| Controller vs Processor | GDPR roles | Controller = determines purposes/means; Processor = processes on behalf |
| GDPR Article 22 vs EU AI Act Article 14 | Automated decision rules | Article 22 = solely automated decisions (GDPR); Article 14 = human oversight (EU AI Act high-risk) |
| NIST GOVERN vs MANAGE | Framework functions | GOVERN = policies/culture; MANAGE = operational monitoring |
| Prohibited vs High-Risk AI | EU AI Act classifications | Article 5 lists prohibited (social scoring, emotion recognition in workplace/school); Annex III lists high-risk |
| MEASURE vs MANAGE | NIST functions | MEASURE = pre-deployment testing; MANAGE = post-deployment monitoring |

## Domain-Specific Gotchas
**Domain 5 (Laws):**  
- GDPR Article 22: solely automated decisions with legal/significant effects  
- GDPR Article 35: DPIA required for high-risk processing  
- EU AI Act Article 5: prohibited AI practices (social scoring, subliminal manipulation, emotion recognition in workplace/education)  
- EU AI Act Article 6-7: high-risk AI classification (Annex III lists use cases)  
- EU AI Act Article 14: human oversight for high-risk AI  

**Domain 4 (Risk/Governance):**  
- NIST AI RMF functions: GOVERN (policies), MAP (context), MEASURE (testing), MANAGE (monitoring)  
- ISO/IEC 42001: AIMS (AI Management System) structure  

**Domain 3 (Responsible AI):**  
- Protected characteristics: race, gender, age, disability, religion  
- Bias types: historical bias, representation bias, measurement bias, aggregation bias  
- Fairness metrics: demographic parity, equalized odds, equal opportunity  

**Domain 2 (Lifecycle):**  
- Design phase: impact assessments, stakeholder engagement  
- Development phase: training data documentation, model cards  
- Deployment phase: monitoring plans, incident response  
- Documentation artifacts: technical documentation, conformity assessment, user instructions  

**Domain 1 (Foundations):**  
- AI system actors: provider, deployer, distributor, importer, user  
- GDPR actors: controller, processor, data subject  
- Roles can overlap (deployer may be controller)
