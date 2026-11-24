**Research Topic**: Empirical Evaluation of Domain Generalization and Adaptation of Software Models for Check-Worthiness Detection When Transitioning from Formal Corpora to Social Media Data.

Problem Statement

Automatic detection of claims that deserve fact-checking (Check-Worthiness Detection) is an important step in automated fact-checking.

However, models trained on formal text corpora, such as political debates, may demonstrate reduced performance when applied to social media data due to differences in linguistic features, text structure, abbreviations, and informal vocabulary.

This research aims to investigate model generalization across different text corpora, the impact of labeled training data volume on domain adaptation, and the influence of text preprocessing on check-worthiness detection performance.

- RQ1 — Zero-Shot Cross-Corpus Transfer

Null Hypothesis (H₀.₁): The mean positive-class F1-score of the CheckThat! 2024-trained bert-base-uncased model on the Twitter test set is greater than or equal to its mean positive-class F1-score on the prevalence-matched CheckThat! 2024 test set (ΔF₁ = F₁,Debates − F₁,Twitter ≤ 0).

Research Hypothesis (H₁.₁): The mean positive-class F1-score of the CheckThat! 2024-trained bert-base-uncased model is lower on the Twitter test set than on the prevalence-matched CheckThat! 2024 test set by a statistically significant margin (ΔF₁ \> 0 at p \< 0.05 via bootstrap test).

- RQ2 — Target-Domain Fine-Tuning Sample Volume

Null Hypothesis (H₀.₂): Increasing the fine-tuning sample size across N ∈ {50, 100, 250, 500} is associated with a zero or negative change in mean positive-class F1-score between N = 50 and N = 500 (F₁,₅₀₀ − F₁,₅₀ ≤ 0).

Research Hypothesis (H₁.₂): A larger target-domain fine-tuning sample size is positively associated with higher check-worthiness detection performance, such that the model fine-tuned on N = 500 tweets achieves a statistically significantly higher mean positive-class F1-score than the model fine-tuned on N = 50 tweets (F₁,₅₀₀ − F₁,₅₀ \> 0 at p \< 0.05, paired bootstrap test).

- RQ3 — Impact of Text Normalization Pipeline vs. Raw Syntax

Null Hypothesis (H₀.₃): The mean positive-class F1-score of the model using unmasked surface syntax (Pipeline B) is less than or equal to the mean positive-class F1-score of the identical model using token-masking normalization (Pipeline A) (F₁,Unmasked − F₁,Masked ≤ 0).

Research Hypothesis (H₁.₃): Holding the model checkpoint (bert-base-uncased) and training set (N = 500 tweets) constant, preserving unmasked surface syntax (Pipeline B) yields a statistically significantly higher mean positive-class F1-score on the held-out Twitter test set than token-masking normalization (Pipeline A) (F₁,Unmasked − F₁,Masked \> 0 at p \< 0.05).

| Research Question | Selected Strategy     | Backup option           |
|-------------------|-----------------------|-------------------------|
| 1                 | Laboratory Experiment | Sample Study            |
| 2                 | Laboratory Experiment | Sample Study            |
| 3                 | Laboratory Experiment | Experimental Simulation |

The strategy selection was approved by the research team and conditionally supported by the strategy-advisor agent.

Strategy Justification

RQ1 — Zero-Shot Cross-Corpus Transfer

Laboratory Experiment enables a controlled comparison of F1-scores across two different corpora while maintaining the same trained BERT model, annotation guidelines, and positive-class prevalence.

RQ2 — Target-Domain Fine-Tuning Sample Volume

Laboratory Experiment allows systematic variation of the labeled training sample size (50, 100, 250, and 500 tweets) while maintaining the same model architecture, hyperparameters, and test set.

RQ3 — Impact of Text Normalization Pipeline vs. Raw Syntax

Laboratory Experiment enables a controlled comparison of two text preprocessing pipelines while keeping the model architecture, training data, evaluation set, and hyperparameters constant.

Trade-offs and Limitations

A/B/C Trade-offs

The selected Laboratory Experiment strategy prioritizes measurement precision and experimental control (B) at the expense of generalizability (A) and contextual realism (C).

Generalizability is limited because the study focuses on a single model architecture and specific datasets. Experimental control is strengthened by maintaining consistent model parameters, evaluation conditions, and data splits. Contextual realism is limited because real social media data is evaluated under artificially controlled conditions.

Research-Specific Limitations

RQ1: Findings may not generalize to other languages, datasets, or model architectures. Differences between corpora cannot be attributed exclusively to language formality.

RQ2: Findings are limited to the selected model architecture, tweet collection, and training configuration.

RQ3: Findings are specific to the selected preprocessing pipelines. The individual effects of numbers, URLs, and punctuation cannot be isolated.

Dataset availability, annotation consistency, computational resources, and statistical procedures require further verification before experimental implementation.
