# Floor 2 Acceptance Testing Log (`question-checker` Skill)

## Part 1: Initial Check of Group's Research Questions — RQ1–RQ3 (Round 1)

I used the 8 criteria exactly as the skill defines them. I only diagnose; I do not rewrite anything.

| Pair | Pass | Partial | Fail |
| :--- | :--- | :--- | :--- |
| **RQ1 / H1.1** | 3 | 5 | 0 |
| **RQ2 / H1.2** | 1 | 7 | 0 |
| **RQ3 / H1.3** | 2 | 5 | 1 |

### RQ1 / H1.1: zero-shot transfer
- **IV:** test-corpus domain (CheckThat! 2024 official test vs. Twitter collection).
- **DV:** positive-class F1, with Precision and Recall listed as secondary.
- **Context:** BERT trained on CheckThat! 2024 Task 1.
- **ERROR: UNDEFINED / VAGUE:** the "Twitter collection" (source, size, language, labeling protocol, positive-class share), the "BERT" variant, and the "official test set".
- **Classification:** Comparative question. The hypothesis is directional and associative.

| Criterion | Status | Justification & notes |
| :--- | :--- | :--- |
| 1. Variables & population | Partial | The DV is clear, but the Twitter collection is undefined. Corpus is a bundle of genre, annotation guidelines and class prevalence, so IV = "domain" is only partly isolated. |
| 2. Deductive grounding | Partial | The Dataset Shift rationale is generic, and the Nenno (2024) support is [UNVERIFIED]. The step from theory to "F1 will drop" is asserted, not derived. |
| 3. Falsifiability | Partial | A clear refuting outcome exists (F1 on Twitter ≥ F1 on the official test). But "statistically significant" has no test, α, or source of variance, since one model gives one F1 per test set. |
| 4. Directionality | Pass | The expected direction is explicit (decrease). |
| 5. Null hypothesis | Pass | H0 is explicit and complementary to H1 (one-tailed). |
| 6. Testability | Partial | F1 is quantitative, but the test and CI procedure are missing. The DV lists three metrics while H1 tests only F1. Also, F1 depends on class prevalence by definition, so a lower F1 on Twitter may reflect a lower positive rate rather than poorer transfer. |
| 7. Form & alignment | Pass | The hypothesis is declarative and answers the RQ. |
| 8. Vague terms | Partial | "Informal" and "significantly" are not operationalized. |

- **Causality:** There are no flagged causal verbs. However, the design cannot attribute the F1 drop to domain alone, because annotation guidelines and prevalence are confounded with it.

### RQ2 / H1.2: learning curve over labeled tweets
- **IV:** number of labeled tweets for fine-tuning. Four levels (50/100/250/500) in the RQ and H, but the IV line also includes 0.
- **DV:** positive-class F1 on a fixed held-out Twitter test set.
- **ERROR: UNDEFINED / VAGUE:** "Base BERT" (vanilla checkpoint or the CheckThat!-trained one from RQ1); subset sampling (nested or independent, stratified or not); test-set size and number of positives; hyperparameter and seed policy.
- **Classification:** Correlation/Comparative (dose–response curve). The hypothesis is directional and compound (monotone growth plus saturation).

| Criterion | Status | Justification & notes |
| :--- | :--- | :--- |
| 1. Variables & population | Partial | The IV is countable, but the 0 level is inconsistent across sections and the base model is undefined. |
| 2. Deductive grounding | Partial | Nenno (2024) and Meng et al. (2024) are [UNVERIFIED]. The prediction of strict monotonicity is not obviously deducible, because BERT fine-tuning on very small samples is commonly reported as unstable [UNVERIFIED]. |
| 3. Falsifiability | Partial | A flat or declining curve refutes H1. "Diminishing marginal gain" has no criterion, so with four noisy points almost any shape can be read as saturation, which is a built-in loophole. |
| 4. Directionality | Pass | The direction is explicit (increase). |
| 5. Null hypothesis | Partial | H0 ("no growth") and H1 ("monotone with saturation") are not exhaustive. Growth without saturation, or non-monotone overall growth, falls under neither. |
| 6. Testability | Partial | No test for monotone trend, no saturation metric, and no repeated runs. If the positive share is low, a 50-tweet sample may contain only a handful of positives. |
| 7. Form & alignment | Partial | The form is declarative, but the levels (0 vs. 50–500) differ between IV, H0 and H1. |
| 8. Vague terms | Partial | "Monotonic", "saturation" and "marginal gain" are undefined quantitatively. |

- Causality flag: H1.2 uses "leads to". Until the protocol states controls for nested/independent subsets, class balance, and validation splits, the causal wording is unsupported.

 RQ3 / H1.3: adapted model vs. ba-claim/bert
- IV: "model configuration". `ERROR: UNDEFINED / VAGUE`, because it bundles at least four things: fine-tuning on target data, preprocessing (raw vs. normalized), training data, checkpoint and hyperparameters.
- DV: positive-class F1 on the same held-out Twitter set.
- ERROR: UNDEFINED / VAGUE:** which RQ2 checkpoint (50, 1
- ## Additional Test — RQ1 Without Hypotheses (18 November 2026)

Skill:question-checker (Floor 2)

Test input:  
RQ1: How well does a check-worthiness detection model trained on a public benchmark generalize to manually labeled Twitter posts from different topics?

Test conditions:  
Only the research question was submitted. No H0 or H1 hypotheses were provided.

Observed result:
- Claude evaluated the research question using the eight criteria.
- It correctly identified missing details about the dataset, evaluation metrics, and model.
- It did not rewrite the research question.
- It stopped and waited for researcher confirmation.
- However, criteria related to missing hypotheses were marked as "Fail (N/A)".

Issue identified:  
When hypotheses are not provided, hypothesis-specific criteria should be marked as "N/A" rather than counted as failures of the research question.

Test status: PARTIAL PASS

Recommended improvement:  
Distinguish between "Fail" and "Not Applicable" when evaluating research questions without hypotheses.

Action: 
Record this issue for future improvement of the question-checker skill.
