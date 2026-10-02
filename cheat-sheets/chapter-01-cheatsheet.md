# AIGP Domain 1 Quick Reference: Foundations of AI Systems

## Core Definitions (2026 BoK)

| Term | Definition | Governance Focus |
|------|------------|------------------|
| **AI System** | Complete deployed solution: model + data pipelines + interfaces + infrastructure + monitoring | System-level risks beyond just model |
| **AI Model** | Trained algorithm/weights only | Model-level risks: bias, accuracy |
| **Foundation Model** | Large pre-trained model adapted for multiple tasks (LLMs, diffusion models) | Dual governance: base + each use case |
| **GPAI** | General-Purpose AI - performs various tasks without task-specific design | Risk varies by deployment context |

## Learning Types - Governance Implications

| Type | How It Learns | Key Governance Concerns |
|------|---------------|-------------------------|
| **Supervised** | Labeled training data | Data quality, labeling bias, representativeness |
| **Unsupervised** | Finds patterns without labels | Pattern validity, cluster meaningfulness |
| **Reinforcement** | Trial-and-error with rewards | Safety bounds on exploration, reward alignment |

## EU AI Act Actor Roles (Articles 16, 23, 24, 26)

| Role | Definition | Primary Obligations | Article |
|------|------------|---------------------|--------|
| **Provider** | Develops AI system or has it developed; places under own name | Conformity assessment, CE marking, technical documentation, risk management | 16 |
| **Deployer** | Uses AI system under their authority (except personal use) | Appropriate deployment, monitoring, human oversight, input data quality | 26 |
| **Importer** | Places AI system from outside EU onto EU market | Verify CE marking, ensure provider compliance, maintain documentation, register system | 23 |
| **Distributor** | Makes AI system available on EU market (not placing under own name) | Verify CE marking, check provider/importer compliance, proper storage/transport | 24 |

**Critical Exam Point**: One organization can have MULTIPLE roles. Example: Import base model (importer) → fine-tune it (provider of new system) → deploy it (deployer).

## Provider vs Deployer Accountability Split

| Responsibility | Provider | Deployer |
|----------------|----------|----------|
| Conformity assessment | ✓ | ✗ |
| CE marking | ✓ | ✗ |
| Model training data quality | ✓ | ✗ |
| Deployment monitoring | ✗ | ✓ |
| Human oversight setup | ✗ | ✓ |
| Input data quality (inference) | ✗ | ✓ |
| Technical documentation | ✓ (create) | ✓ (maintain access) |

**Exam Trap**: Deployer can't skip their obligations because provider did conformity assessment - each has separate duties.

## AI System Components - Risk Assessment Points

```
┌─────────────────────────────────────┐
│  AI SYSTEM (complete governance scope) │
├─────────────────────────────────────┤
│ 1. DATA                             │
│    - Training data (quality, bias)  │
│    - Inference data (drift, validation) │
├─────────────────────────────────────┤
│ 2. MODEL                            │
│    - Algorithm, weights, parameters │
│    - Accuracy, fairness, robustness │
├─────────────────────────────────────┤
│ 3. INTERFACE                        │
│    - API, UI, integration points    │
│    - Misuse scenarios, access control│
├─────────────────────────────────────┤
│ 4. DEPLOYMENT ENVIRONMENT           │
│    - Infrastructure, monitoring     │
│    - Logging, incident response     │
└─────────────────────────────────────┘
```

## Training Data vs Inference Data Governance

| Aspect | Training Data | Inference Data |
|--------|---------------|----------------|
| **When** | Model development phase | Production/deployment phase |
| **Volume** | Large historical dataset | Individual inputs, ongoing |
| **Key Controls** | Representativeness, bias testing, quality validation | Drift monitoring, input validation, adversarial detection |
| **Governance Focus** | Is dataset appropriate? Any systemic bias? | Does input match training distribution? Any attacks? |
| **Privacy** | Anonymization, consent for training | Real-time PII handling, purpose limitation |

## Foundation Models - Dual-Level Governance

**Base Model Level**:
- Training data quality and bias
- Known capabilities and limitations  
- Safety testing results
- Model cards/documentation

**Use Case Level** (for EACH application):
- Fine-tuning data quality
- Application-specific risks
- Deployment context controls
- Use-case monitoring

**Exam Point**: Fine-tuning doesn't reset governance - both levels need controls.

## Common Exam Traps

❌ **WRONG**: "Model and system are same thing" → System includes model + data + interfaces + infrastructure  
❌ **WRONG**: "Deployer has no obligations if provider did conformity assessment" → Both have distinct obligations  
❌ **WRONG**: "Importer just passes through; provider is responsible" → Importer must verify compliance, maintain docs  
❌ **WRONG**: "Foundation model fine-tuned once = governs once" → Each downstream use case needs governance  
❌ **WRONG**: "Training data governed = done" → Inference data needs ongoing monitoring for drift

## Quick Scenario Mapping

Scenario: "US company makes model → EU company adapts it → Hospital uses it → Vendor sells it"
- US company = **Provider** (of base model)
- EU company = **Importer** (brings to EU) + **Provider** (creates adapted system)  
- Hospital = **Deployer** (uses in operations)
- Vendor = **Distributor** (makes available on market)

Each role = different Article, different obligations.
