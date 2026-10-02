# Chapter 4: Privacy, Safety, and Societal Impacts of AI - Cheat Sheet

## Privacy-Enhancing Technologies

| Technique | When to Use | Key Parameter | Privacy Strength |
|-----------|-------------|---------------|------------------|
| **Differential Privacy** | Publishing aggregate statistics, query results on centralized data | Epsilon (ε): lower = stronger privacy | ε<1: strong, ε=1-3: moderate, ε>3: weak |
| **Federated Learning** | Training when data cannot be centralized (data locality requirements) | Number of rounds, edge devices | Data never leaves local devices |
| **Synthetic Data** | Testing/development when real data unavailable or too sensitive | Generation method (GANs, statistical) | High privacy, lower fidelity for edge cases |

### Differential Privacy Numbers
- **Strong privacy**: ε = 0.1-0.5 (very noisy results, high privacy)
- **Moderate**: ε = 1.0-3.0 (balanced privacy-utility)
- **Weak privacy**: ε = 5.0+ (accurate results, limited privacy protection)
- **Privacy budget**: Total epsilon across all queries - once exhausted, no more queries allowed

### Federated Learning Key Points
- **Transmitted**: Model updates (gradients/weights) only
- **NOT transmitted**: Raw training data
- **Training location**: Edge devices/local nodes
- **Aggregation**: Central server combines updates
- **Use case**: Medical data across hospitals, mobile keyboard predictions, cross-silo collaboration

## AI Safety and Robustness

| Attack Type | Phase | Description | Defense |
|-------------|-------|-------------|----------|
| **Model Poisoning** | Training time | Inject malicious/mislabeled data into training set | Data validation, anomaly detection in training data |
| **Adversarial Examples** | Inference time | Crafted inputs with imperceptible perturbations that fool model | Adversarial training, input validation, ensemble methods |
| **Gradient-based attacks** | Inference time | Use gradients (FGSM, PGD) to find minimal perturbations | Gradient masking, defensive distillation |

### Robustness Testing Methods
- **FGSM** (Fast Gradient Sign Method): Fast, finds adversarial examples using sign of gradient
- **PGD** (Projected Gradient Descent): Iterative, stronger attack, finds minimal perturbations
- **Output validation**: Check predictions against expected ranges, consistency checks

## Employment AI: Legal and Ethical Issues

### Key US Laws
- **Title VII (Civil Rights Act)**: Prohibits employment discrimination based on race, color, religion, sex, national origin
- **ADA** (Americans with Disabilities Act): Prohibits disability discrimination
- **EEOC Guidelines**: Four-Fifths Rule for disparate impact

### Discrimination Types
| Type | Definition | Example | Legal Test |
|------|------------|---------|------------|
| **Disparate Treatment** | Intentional different treatment based on protected class | Using gender as explicit hiring criterion | Direct evidence of intent |
| **Disparate Impact** | Neutral policy with discriminatory effect | AI recommends 75% male candidates from 50-50 pool | Four-Fifths Rule: selection rate ≥80% of highest group |

### Four-Fifths Rule
- **Threshold**: Protected group selection rate must be ≥80% of highest group rate
- **Example**: If 50% of Group A hired → Group B must be ≥40% hired
- **Below threshold**: Triggers disparate impact investigation

### High-Risk Employment Use Cases
1. **Resume screening**: Bias from historical hiring data
2. **Worker surveillance**: Productivity monitoring, automated warnings
3. **Automated termination**: Requires human oversight - automated decision pipeline is high governance risk

## Credit and Lending AI

### US Regulations
- **ECOA** (Equal Credit Opportunity Act) + **Regulation B**: Prohibit credit discrimination, require disparate impact analysis
- **FCRA** (Fair Credit Reporting Act): Credit reporting disclosure requirements
- **Fair Lending Laws**: Apply even when protected characteristics not explicit inputs

### EU Regulations
- **Consumer Credit Directive**: Fairness in lending across EU
- **GDPR Article 22**: Right to explanation for automated decisions

### Key Compliance Points
- Disparate impact analysis required even without using protected characteristics as inputs
- **Proxy variables** (zip code, education, employment) can create discrimination
- Lender must prove **business necessity** if disparate impact found
- Adverse action notices required when credit denied

## Healthcare AI: Safety and Liability

### System Types and Liability
| System Type | Decision Authority | Primary Liability | Validation |
|-------------|-------------------|-------------------|------------|
| **Clinical Decision Support (CDS)** | Physician makes final decision | Physician/healthcare provider | FDA may not regulate as medical device |
| **Diagnostic AI** | AI makes autonomous diagnosis | Complex - may involve vendor, provider, hospital | FDA regulation as medical device |

### Safety Validation Requirements
- **Clinical trials**: For diagnostic systems, required evidence of safety/efficacy
- **Adverse event reporting**: Required for FDA-regulated medical AI
- **Continuous monitoring**: Model performance on real patients vs validation set
- **Edge case testing**: Rare conditions, atypical presentations

### Liability Allocation Principles
1. **Licensed professional retains responsibility** for final clinical decisions when using CDS
2. **Vendor liability**: Product defects, misrepresentation of capabilities, failure to validate
3. **Hospital liability**: Vicarious liability for staff, systemic validation failures
4. **Key distinction**: CDS assists → physician liable; Diagnostic AI decides → complex liability

## Exam Tips
- **Privacy**: Lower epsilon = stronger privacy (inverse relationship)
- **Federated vs Differential**: Federated = can't centralize data; Differential = publishing statistics
- **Poisoning vs Adversarial**: Training-time vs inference-time attacks
- **Disparate impact**: Can occur WITHOUT using protected characteristics - test for proxy variables
- **Four-Fifths**: 80% threshold is key number for EEOC disparate impact
- **Healthcare liability**: CDS = physician liable; diagnostic AI = complex shared liability
- **High-stakes decisions**: Employment termination, credit denial, medical diagnosis → require human oversight
