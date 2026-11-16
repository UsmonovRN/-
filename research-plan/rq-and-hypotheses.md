# Research Questions, Hypotheses, and Verification Criteria (Floor 2 — Revised)

**Research Topic:** Empirical Evaluation of Domain Generalization and Adaptation of Software Models for Check-Worthiness Detection When Transitioning from Formal Corpora to Social Media Data.

**Target Corpus & Experimental Context (Operational Definitions):**
- **Source Corpus:** English subset of `CheckThat! 2024 Task 1` political debates (official train/validation/test splits, annotated under CLEF-2024 check-worthiness guidelines).
- **Target Corpus (`Twitter` Collection):** A fixed dataset of $N = 1,000$ English public tweets (500 held-out test tweets + 500 pool tweets for fine-tuning), fully anonymized prior to processing (`@handles` replaced with generic placeholders to remove PII) and manually annotated by two independent coders using the exact same CLEF-2024 check-worthiness guidelines (inter-annotator agreement measured via Cohen's $\kappa \ge 0.70$).
- **Base Architecture:** `bert-base-uncased` fine-tuned on the `CheckThat! 2024 Task 1` training split with fixed random seeds (5 runs) and paired bootstrap resampling ($B = 1,000$, $\alpha = 0.05$) for statistical comparisons.

---

## Part 1. Criteria for a Good Hypothesis (Based on Slides 22 and 32 of Meeting 2)
1. **Relationship Between Variables and Population:** The Independent Variable (IV), Dependent Variable (DV), and target data corpus are clearly defined and measurable.
2. **Deductive Grounding in Theory:** The hypothesis is deductively derived from existing theory and prior empirical studies (2024), rather than invented arbitrarily.
3. **Falsifiability (per Karl Popper):** A specific empirical outcome exists that could refute the hypothesis; circular logic and built-in "loopholes" are absent.
4. **Directionality:** The research hypothesis ($H_1$) clearly specifies the direction of the expected change or difference.
5. **Presence of a Null Hypothesis ($H_0$):** Every research hypothesis is paired with an explicit, exhaustive null hypothesis stating the absence of the predicted effect.
6. **Empirical Testability:** Variables are operationalized through a primary quantitative metric (positive-class `F1-score`) with a defined statistical test ($\alpha = 0.05$).
7. **Declarative Form:** The hypothesis is formulated as an affirmative statement (not a question) and directly answers the research question.
8. **Conciseness and Unambiguity:** Vague evaluative words ("better", "good", "aggressive") without quantitative definitions are absent.

---

## Part 2. Three Research Questions and Their Hypotheses (Revised After Agent Critique)

### Research Question 1 (RQ1 — Zero-Shot Cross-Corpus Transfer)
- **Question:** How does positive-class `F1-score` change when a `bert-base-uncased` model trained on the formal `CheckThat! 2024 Task 1` debate training set is evaluated without fine-tuning on the anonymized `Twitter` test set ($n = 500$) compared to the official `CheckThat! 2024` debate test set, when both corpora share identical annotation guidelines and are stratified to an equal positive-class prevalence (25%)?
- **Independent Variable (IV):** Linguistic genre of the evaluation corpus (formal political debate transcripts in `CheckThat! 2024` test set vs. informal short posts in the prevalence-matched `Twitter` test set).
- **Dependent Variable (DV):** Positive-class `F1-score` (evaluated across $B = 1,000$ bootstrap resamples at $\alpha = 0.05$; `Precision` and `Recall` reported as diagnostic metrics).
- **Theoretical Rationale:** Under Covariate Shift theory and cross-dataset empirical findings by Nenno (2024), out-of-vocabulary slang, abbreviations, and fragmented syntax in social media shift feature representations away from formal training distributions, lowering classification `F1-score` even when label definitions and class prevalence are held constant.
- **Null Hypothesis ($H_{0.1}$):** The mean positive-class `F1-score` of the `CheckThat! 2024`-trained `bert-base-uncased` model on the `Twitter` test set is greater than or equal to its mean positive-class `F1-score` on the prevalence-matched `CheckThat! 2024` test set ($\Delta F_1 = F_{1,\text{Debates}} - F_{1,\text{Twitter}} \le 0$).
- **Research Hypothesis ($H_{1.1}$ — Directional, Comparative):** The mean positive-class `F1-score` of the `CheckThat! 2024`-trained `bert-base-uncased` model is lower on the `Twitter` test set than on the prevalence-matched `CheckThat! 2024` test set by a statistically significant margin ($\Delta F_1 > 0$ at $p < 0.05$ via bootstrap test).

---

### Research Question 2 (RQ2 — Target-Domain Fine-Tuning Sample Volume)
- **Question:** What is the association between the number of stratified target-domain `Twitter` training examples ($N \in \{50, 100, 250, 500\}$ nested subsets) used to further fine-tune the `CheckThat! 2024`-initialized `bert-base-uncased` checkpoint and its positive-class `F1-score` on the fixed held-out `Twitter` test set ($n = 500$)?
- **Independent Variable (IV):** Target-domain fine-tuning sample size ($N \in \{50, 100, 250, 500\}$ nested, class-stratified labeled tweets, with identical hyperparameters averaged across 5 random seeds).
- **Dependent Variable (DV):** Mean positive-class `F1-score` across 5 random seeds on the fixed held-out `Twitter` test set ($n = 500$).
- **Theoretical Rationale:** Domain adaptation theory (Nenno, 2024; Meng et al., 2024) posits that fine-tuning a pre-trained encoder on target-domain examples aligns token embeddings with target syntax, yielding higher positive-class `F1-score` as labeled sample size increases.
- **Null Hypothesis ($H_{0.2}$):** Increasing the fine-tuning sample size across $N \in \{50, 100, 250, 500\}$ is associated with a zero or negative change in mean positive-class `F1-score` between $N = 50$ and $N = 500$ ($F_{1,500} - F_{1,50} \le 0$).
- **Research Hypothesis ($H_{1.2}$ — Directional, Associative):** A larger target-domain fine-tuning sample size is positively associated with higher check-worthiness detection performance, such that the model fine-tuned on $N = 500$ tweets achieves a statistically significantly higher mean positive-class `F1-score` than the model fine-tuned on $N = 50$ tweets ($F_{1,500} - F_{1,50} > 0$ at $p < 0.05$, paired bootstrap test).

---

### Research Question 3 (RQ3 — Impact of Text Normalization Pipeline vs. Raw Syntax)
- **Question:** How does positive-class `F1-score` on the held-out `Twitter` test set ($n = 500$) differ when the same `bert-base-uncased` architecture (fine-tuned on $N = 500$ tweets) is trained and evaluated using a token-masking normalization pipeline (replacing numbers with `<number>` tokens and removing URLs/punctuation markers) versus preserving unmasked surface tokens (retaining numbers, URL tokens, and punctuation), while keeping training data, hyperparameters, and model checkpoint identical?
- **Independent Variable (IV):** Text preprocessing pipeline applied prior to tokenization (Pipeline A: token-masking normalization removing URLs and masking numbers vs. Pipeline B: unmasked surface syntax retaining numbers and URL indicators; both pipelines anonymize `@user` handles for PII compliance).
- **Dependent Variable (DV):** Mean positive-class `F1-score` on the held-out `Twitter` test set ($n = 500$), compared via McNemar's / paired bootstrap test ($\alpha = 0.05$).
- **Theoretical Rationale:** Check-worthiness studies (Hasanain et al., 2024; Nenno, 2024) note that factual claims in social media frequently rely on specific numerical statistics and external links as evidence markers; stripping numbers and URLs removes discriminative features needed by the classifier.
- **Null Hypothesis ($H_{0.3}$):** The mean positive-class `F1-score` of the model using unmasked surface syntax (Pipeline B) is less than or equal to the mean positive-class `F1-score` of the identical model using token-masking normalization (Pipeline A) ($F_{1,\text{Unmasked}} - F_{1,\text{Masked}} \le 0$).
- **Research Hypothesis ($H_{1.3}$ — Directional, Comparative):** Holding the model checkpoint (`bert-base-uncased`) and training set ($N = 500$ tweets) constant, preserving unmasked surface syntax (Pipeline B) yields a statistically significantly higher mean positive-class `F1-score` on the held-out `Twitter` test set than token-masking normalization (Pipeline A) ($F_{1,\text{Unmasked}} - F_{1,\text{Masked}} > 0$ at $p < 0.05$).

---

## Part 3. Documentation of Revisions Made After `question-checker` Critique (Per Slide 28 & 37)
1. **Defined Target Corpus & PII Protection:** Explicitly defined the `Twitter` dataset size ($N = 1,000$), annotation guideline alignment (CLEF-2024), inter-annotator agreement ($\kappa \ge 0.70$), and mandatory `@user` anonymization for privacy compliance.
2. **Controlled Confounding Variables in RQ1 & RQ3:** In `RQ1`, controlled for class-prevalence differences by specifying prevalence-matched evaluation (25%). In `RQ3`, resolved the `Fail` status by isolating the **Text Preprocessing Pipeline** on the exact same model architecture and training split instead of confounding preprocessing with an external model (`ba-claim/bert`).
3. **Removed Popperian Loophole & Causal Wording in RQ2:** Replaced the causal verb "leads to" with associative phrasing, aligned sample levels ($N \in \{50, 100, 250, 500\}$), and replaced the vague "learning curve saturation" clause with an exhaustive, falsifiable test comparing $F_{1,500}$ against $F_{1,50}$.
