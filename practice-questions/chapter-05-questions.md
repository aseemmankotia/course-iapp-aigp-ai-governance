## Chapter 5: NIST AI Risk Management Framework (AI RMF) — Practice Questions

**Q1.** A multinational financial services company is implementing an AI-powered loan approval system that will operate in both the EU and US. The AI governance team needs to establish a framework that will help them comply with the EU AI Act while also meeting US regulatory expectations. Which approach BEST addresses their needs?

A) Implement the EU AI Act requirements as primary framework since it's legally binding, and use NIST AI RMF only for US operations
B) Use NIST AI RMF as the foundational framework and leverage its crosswalk to map controls to EU AI Act requirements
C) Develop separate governance frameworks for each jurisdiction to ensure full compliance with local requirements
D) Adopt ISO/IEC 42001 as it's an international standard that automatically ensures compliance with both frameworks

<details>
<summary>Answer</summary>

**Correct: B**

NIST AI RMF is designed as a voluntary framework with explicit crosswalks to other frameworks including the EU AI Act. This allows organizations to establish unified governance while mapping to multiple regulatory requirements. The framework's flexibility enables compliance mapping without duplicating efforts.

**Why the others are wrong:**
- While EU AI Act is legally binding in EU, this creates siloed governance and doesn't leverage the NIST framework's crosswalk capabilities, leading to duplicated effort and potential gaps
- Separate frameworks create operational complexity, inconsistent risk assessments, and miss the opportunity to use NIST's crosswalk feature that specifically addresses multi-jurisdiction compliance
- ISO/IEC 42001 provides requirements for AI management systems but doesn't automatically ensure compliance — it still requires mapping and gap analysis, and lacks the specific crosswalk utilities NIST provides

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During the MAP function of NIST AI RMF implementation, a healthcare AI team identifies that their diagnostic imaging system processes protected health information and may produce recommendations that directly impact patient treatment decisions. According to NIST AI RMF, what should be their NEXT step?

A) Immediately implement the MANAGE function controls to address identified risks
B) Complete risk categorization by mapping impacts across all trustworthy characteristics (safety, security, fairness, privacy, etc.)
C) Develop detailed metrics and benchmarks as specified in the MEASURE function
D) Establish governance policies and oversight structures before proceeding further

<details>
<summary>Answer</summary>

**Correct: B**

The MAP function follows a specific sequence: context establishment → categorization → risk mapping across the AI lifecycle. After identifying context (healthcare data, treatment decisions), the next step is categorization, which means mapping impacts across ALL trustworthy characteristics to understand the full risk profile before measuring or managing.

**Why the others are wrong:**
- MANAGE comes after MEASURE — jumping directly to controls skips critical steps of understanding HOW to measure risks and establishing baselines
- MEASURE requires completion of MAP first — you cannot establish meaningful metrics without first completing risk categorization and understanding which trustworthy characteristics are most impacted
- GOVERN is the overarching function that runs continuously, not a sequential step — it should already be established before MAP begins, and this would be going backward in the process

</details>

---

**Q3.** A retail company's AI system for inventory optimization shows reliable performance in testing but the procurement team cannot understand why the system recommends specific vendor selections. The AI governance lead must address this issue using NIST AI RMF trustworthy characteristics. Which characteristic is PRIMARILY at issue, and what is the key distinction the exam tests?

A) Explainability/Interpretability — the system lacks interpretability (understanding how decisions are made), not explainability (communicating decisions to stakeholders)
B) Accountability/Transparency — the system lacks transparency in its decision-making process
C) Valid/Reliable — the system's reliability is in question despite testing performance
D) Explainability/Interpretability — the system lacks explainability (communicating decisions), not interpretability (technical understanding)

<details>
<summary>Answer</summary>

**Correct: A**

NIST AI RMF distinguishes between interpretability (technical understanding of how the model works internally) and explainability (ability to communicate decisions to stakeholders). The procurement team's inability to understand WHY decisions are made is an interpretability issue — they need to understand the decision-making logic, not just receive explanations of outputs.

**Why the others are wrong:**
- Transparency relates to disclosure of AI system information, data sources, and limitations — not the same as understanding decision logic. This is a commonly confused concept on the exam
- Valid/Reliable relates to technical performance and consistency — the system IS performing reliably in testing, so this is not the primary issue here
- This reverses the definitions — interpretability is about HOW decisions are made (technical understanding), while explainability is about communicating those decisions. The exam specifically tests this distinction

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** An AI system categorized as 'high-risk' under the EU AI Act is being evaluated using NIST AI RMF. The team notes that NIST uses a different risk tiering approach. What is the CRITICAL difference that affects governance implementation?

A) EU AI Act uses fixed risk categories (unacceptable, high, limited, minimal) based on use case, while NIST AI RMF uses context-dependent risk assessment across trustworthy characteristics without preset tiers
B) NIST AI RMF has four risk levels (critical, high, medium, low) that must be mapped to EU AI Act categories
C) EU AI Act and NIST AI RMF both use risk-based approaches but EU focuses on technical risks while NIST focuses on business risks
D) NIST AI RMF categorizes by AI type (generative, predictive, etc.) while EU AI Act categorizes by deployment sector

<details>
<summary>Answer</summary>

**Correct: A**

This is a heavily tested distinction: EU AI Act assigns fixed risk categories based on the use case (e.g., biometric identification = high-risk automatically), while NIST AI RMF does NOT have preset risk tiers. Instead, NIST assesses risk contextually across all trustworthy characteristics, allowing organizations to determine risk levels based on their specific implementation.

**Why the others are wrong:**
- NIST AI RMF does NOT define preset risk levels — it's context-dependent. This is a fundamental misunderstanding of NIST's voluntary, flexible approach versus EU's prescriptive categorization
- Both address technical and business risks — the distinction is in HOW risk is tiered (preset categories vs. contextual assessment), not WHAT types of risks are considered
- Neither framework categorizes primarily by AI type or sector — EU AI Act categorizes by USE CASE (e.g., employment decisions, law enforcement), and NIST by contextual impact assessment

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A company has completed the GOVERN and MAP functions of NIST AI RMF. For the MEASURE function, they need to establish metrics for their customer service chatbot. Which approach BEST aligns with NIST AI RMF's MEASURE function guidance?

A) Establish metrics ONLY for the trustworthy characteristics identified as high-risk during the MAP function
B) Develop metrics and benchmarks for ALL seven trustworthy characteristics, with emphasis on those identified as higher risk during MAP
C) Focus metrics exclusively on model performance (accuracy, precision, recall) as these are the foundation for all trustworthy characteristics
D) Implement the metrics specified in the NIST AI RMF Playbook's suggested actions without customization

<details>
<summary>Answer</summary>

**Correct: B**

NIST AI RMF's MEASURE function requires establishing metrics and benchmarks for ALL trustworthy characteristics (valid/reliable, safe, secure/resilient, accountable/transparent, explainable/interpretable, privacy-enhanced, fair with harmful bias managed), with appropriate emphasis based on the risk mapping from the MAP function. This ensures comprehensive coverage while prioritizing resources.

**Why the others are wrong:**
- Measuring only high-risk characteristics creates blind spots — risks can emerge in areas initially deemed lower risk, and NIST emphasizes comprehensive baseline measurement
- Technical performance metrics are necessary but insufficient — NIST AI RMF explicitly requires measuring across all trustworthy characteristics including fairness, privacy, explainability, etc., not just model performance
- The Playbook provides SUGGESTED actions and examples, not prescriptive requirements — organizations must customize metrics to their specific context as identified during MAP. The framework is voluntary and flexible

</details>

---

**Q6.** During a NIST AI RMF implementation audit, the CISO discovers that the AI engineering team has completed MAP, MEASURE, and MANAGE functions but has no formal GOVERN function in place. What is the PRIMARY issue with this approach?

A) This violates the sequential order of NIST AI RMF implementation — GOVERN must be completed first
B) Without GOVERN, there is no oversight structure to ensure policies, roles, and accountability are maintained throughout the AI lifecycle, making other functions ineffective
C) MANAGE function cannot be properly implemented without GOVERN since they are interdependent
D) This is acceptable as GOVERN is an optional function for organizations with existing risk management frameworks

<details>
<summary>Answer</summary>

**Correct: B**

GOVERN is not just first sequentially — it's the OVERARCHING function that runs continuously. It establishes policies, roles, culture, and oversight structures that enable and sustain the other three functions. Without GOVERN, MAP/MEASURE/MANAGE lack the organizational structure, accountability, and policy foundation to be effective or sustainable.

**Why the others are wrong:**
- While GOVERN should be established early, this answer misses the critical point — GOVERN is not just a sequential first step but a continuous, overarching function that enables all others
- While MANAGE and GOVERN are related, stating they're interdependent misses the broader issue — ALL functions (MAP, MEASURE, MANAGE) require GOVERN's oversight structure, not just MANAGE
- GOVERN is NOT optional in NIST AI RMF — it's one of the four core functions. Organizations may integrate it with existing frameworks, but the governance elements must be present for NIST AI RMF implementation

</details>

---

**Q7.** A financial institution uses NIST AI RMF and wants to also demonstrate alignment with OECD AI Principles for a multinational partnership. According to NIST AI RMF's crosswalk approach, what is the MOST effective strategy?

A) Map NIST AI RMF trustworthy characteristics to OECD AI Principles using the framework's crosswalk guidance, documenting how existing controls satisfy both
B) Implement OECD AI Principles separately as NIST AI RMF is US-specific and incompatible with international principles
C) Replace NIST AI RMF with OECD AI Principles since OECD has broader international recognition
D) Use ISO/IEC 42001 as an intermediary framework to bridge NIST AI RMF and OECD AI Principles

<details>
<summary>Answer</summary>

**Correct: A**

NIST AI RMF explicitly provides crosswalks to multiple frameworks including OECD AI Principles. The crosswalk approach allows organizations to map their existing NIST controls to other frameworks' requirements, demonstrating alignment without duplicating governance structures. This is a core feature of NIST's design as a voluntary, flexible framework.

**Why the others are wrong:**
- NIST AI RMF is designed for international use with explicit crosswalks to global frameworks — it's voluntary and not US-specific in scope. This misunderstands the framework's purpose and international applicability
- This creates unnecessary disruption — NIST AI RMF can demonstrate OECD alignment through crosswalks. The exam tests whether candidates understand the crosswalk feature versus thinking frameworks must be replaced
- While ISO/IEC 42001 can complement NIST, it's not necessary as an intermediary — NIST already provides direct crosswalks to OECD. This adds complexity without benefit

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** An e-commerce company implementing NIST AI RMF for their recommendation engine has completed initial MEASURE function metrics. During the MANAGE function, they discover bias in recommendations for certain demographic groups. According to NIST AI RMF's MANAGE function, what should be their immediate response?

A) Disable the AI system immediately until bias is eliminated, as required by the 'fair with harmful bias managed' trustworthy characteristic
B) Document the bias as an AI incident, assess risk severity, implement risk response controls, and establish continuous monitoring with stakeholder communication
C) Return to the MAP function to re-categorize the system's risk level before taking any action
D) Adjust the MEASURE function metrics to better detect bias patterns, then proceed with risk management

<details>
<summary>Answer</summary>

**Correct: B**

NIST AI RMF's MANAGE function encompasses risk response, continuous improvement, and incident response. When issues are discovered, the proper response includes: documenting as incident, assessing severity, implementing appropriate controls (which may or may not include disabling), ongoing monitoring, and stakeholder communication. This reflects risk MANAGEMENT, not risk elimination.

**Why the others are wrong:**
- 'Fair with harmful bias MANAGED' does not mean bias ELIMINATED — NIST recognizes bias management as ongoing risk mitigation, not absolute elimination. Immediate system shutdown may be appropriate for severe cases but isn't automatically required
- Re-categorizing during MAP is not the immediate response to a discovered issue — MANAGE function specifically handles response to identified risks. Going back to MAP would delay addressing an active issue
- While metrics may need refinement, the immediate response to discovered bias is in MANAGE (risk response and incident handling), not adjusting measurement approaches. This confuses the functions' purposes

</details>

---

