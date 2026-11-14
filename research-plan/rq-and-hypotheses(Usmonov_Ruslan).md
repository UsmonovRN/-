# Research Questions, Hypotheses, and Verification Criteria (Floor 2)

**Research Topic:** Empirical Evaluation of Domain Generalization and Adaptation of Software Models for Check-Worthiness Detection When Transitioning from Formal Corpora to Social Media Data.

---

## Part 1. Criteria for a Good Hypothesis (Based on Slides 22 and 32 of Meeting 2)
1. **Relationship Between Variables and Population:** The Independent Variable (IV), Dependent Variable (DV), and target data corpus are clearly defined and measurable.
2. **Deductive Grounding in Theory:** The hypothesis is deductively derived from existing theory and prior empirical studies (2024), rather than invented arbitrarily.
3. **Falsifiability (per Karl Popper):** A specific empirical outcome exists that could refute the hypothesis; circular logic and built-in "loopholes" are absent.
4. **Directionality:** The research hypothesis ($H_1$) clearly specifies the direction of the expected change or difference (decreases / monotonically increases / higher).
5. **Presence of a Null Hypothesis ($H_0$):** Every research hypothesis is paired with an explicit null hypothesis stating the absence of a relationship or difference.
6. **Empirical Testability:** Variables are operationalized through standard quantitative metrics (`F1-score`, `Precision`, `Recall`).
7. **Declarative Form:** The hypothesis is formulated as an affirmative statement (not a question) and serves as a direct tentative answer to the research question.
8. **Conciseness and Unambiguity:** Vague evaluative words ("better", "good", "proper") without a specified measurement metric are absent.

---

## Part 2. Three Research Questions and Their Hypotheses

### Research Question 1 (RQ1 — Cross-Dataset Model Transfer Without Adaptation)
- **Question:** How does the binary classification performance of check-worthy claims (measured by positive-class `F1-score`) change when a pre-trained BERT transformer model is transferred from a formal political debate corpus (`CheckThat! 2024 Task 1`) to an informal social media corpus (`Twitter`) without additional fine-tuning (Zero-shot Cross-Dataset Transfer)?
- **Independent Variable (IV):** Domain (genre) of the evaluation dataset (formal debate utterances in `CheckThat! 2024` vs. informal user posts on `Twitter`).
- **Dependent Variable (DV):** Check-worthy claim detection performance (positive-class `F1-score`, as well as `Precision` and `Recall`).
- **Theoretical Rationale:** According to Dataset Shift theory and empirical findings by Nenno (2024), Check-Worthiness models lose generalization ability when the genre, lexicon, and positive-class proportion change.
- **Null Hypothesis ($H_{0.1}$):** The positive-class `F1-score` of the BERT model trained on `CheckThat! 2024`, when evaluated on the `Twitter` test collection without fine-tuning, does not differ from (or exceeds) its `F1-score` on the official `CheckThat! 2024` test set.
- **Research Hypothesis ($H_{1.1}$ — Directional):** When transferring a BERT model trained on the `CheckThat! 2024` corpus to the `Twitter` test collection without adaptation, the positive-class `F1-score` decreases statistically significantly compared to the official `CheckThat! 2024` test set.

---

### Research Question 2 (RQ2 — Impact of Labeled Data Volume During Adaptation)
- **Question:** How does increasing the volume of the target `Twitter` training sample (50, 100, 250, and 500 manually labeled examples) during fine-tuning of the base BERT model affect check-worthy claim detection performance (positive-class `F1-score`) on an independent `Twitter` test set?
- **Independent Variable (IV):** Number of labeled `Twitter` messages used for fine-tuning the model (0, 50, 100, 250, 500 tweets).
- **Dependent Variable (DV):** Positive-class `F1-score` on a fixed held-out `Twitter` test sample.
- **Theoretical Rationale:** According to Domain Adaptation theory and studies by Nenno (2024) and Meng et al. (2024), fine-tuning a transformer on target-domain examples reduces Dataset Shift, providing a monotonic increase in performance with gradual saturation of the learning curve.
- **Null Hypothesis ($H_{0.2}$):** Increasing the target fine-tuning sample volume from 50 to 500 labeled tweets does not lead to an increase in the positive-class `F1-score` on the independent `Twitter` test set.
- **Research Hypothesis ($H_{1.2}$ — Directional):** Increasing the target fine-tuning sample volume (50, 100, 250, 500 labeled tweets) leads to a monotonic increase in the positive-class `F1-score` on the `Twitter` test set with diminishing marginal gains (learning curve saturation effect).

---

### Research Question 3 (RQ3 — Comparison of the Adapted Model and an External Model on "Live" Language)
- **Question:** How does the detection performance of check-worthy tweets (positive-class `F1-score`) differ between the BERT model fine-tuned on our collection of raw ("live") tweets in RQ2 and an off-the-shelf external model (`ba-claim/bert`) with a standard text cleaning pipeline (replacing `@user` and numbers with tokens, removing links) on the exact same held-out `Twitter` sample?
- **Independent Variable (IV):** Software configuration type of the model (the model adapted to informal syntax from RQ2 vs. the external `ba-claim/bert` model with aggressive text normalization and no fine-tuning).
- **Dependent Variable (DV):** Positive-class `F1-score` on a single held-out `Twitter` test sample.
- **Theoretical Rationale:** According to the CheckThat! 2024 competition overview (Hasanain et al., 2024) and the analysis by Nenno (2024), template token masking removes important contextual signals of informal speech, whereas fine-tuning on natural social media syntax preserves informative features.
- **Null Hypothesis ($H_{0.3}$):** There is no difference in `F1-score` between the adapted BERT model (from RQ2) and the external `ba-claim/bert` model (or the external model achieves a higher `F1-score`) on the held-out sample of informal `Twitter` posts.
- **Research Hypothesis ($H_{1.3}$ — Directional):** The BERT model fine-tuned on the target `Twitter` collection (RQ2) achieves a higher positive-class `F1-score` on "live" `Twitter` language compared to the off-the-shelf external `ba-claim/bert` model without fine-tuning.
