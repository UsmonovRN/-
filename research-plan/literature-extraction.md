# Literature Extraction — Claim Check-Worthiness

## 1. Scope and verification

This document combines the initial pilot with additional full-text screening and extraction.

- Review date: 2026-11-25.
- Reviewer:  AI-assisted review.
- Human check: Performed for the decisions and evidence recorded below. Check was performed by Evgeniy Sudman and Daniil Vakhrushev.
- Coverage: 13 records; 12 included in the main extraction, one excluded.

“Not verified” means that this review has not established the information. It does not mean that the paper omits it.

The existing RQ1–RQ3 remain unchanged. LRQ mappings below distinguish direct evidence from related methodological evidence.

## 2. References and screening decisions

| ID | Reference and primary source | Decision | Reason and relevance |
|---|---|---|---|
| P1 | Jaradat et al. (2018). *ClaimRank: Detecting Check-Worthy Claims in Arabic and English*. NAACL-HLT Demonstrations, 26–30. https://aclanthology.org/N18-5006/ | Include | Direct check-worthiness system; relevant to datasets, labels and ranking evaluation (LRQ4). |
| P2 | Wright and Augenstein (2020). *Claim Check-Worthiness Detection as Positive Unlabelled Learning*. Findings of EMNLP, 476–488. https://aclanthology.org/2020.findings-emnlp.43/ | Include | Studies transfer and incomplete positive labels. Relevant to LRQ1 and LRQ4, but target-domain training prevents treating its transfer results as zero-shot evidence. |
| P3 | Majer and Šnajder (2024). *Claim Check-Worthiness Detection: How Well do LLMs Grasp Annotation Guidelines?* FEVER, 245–263. https://aclanthology.org/2024.fever-1.27/ | Include | Direct check-worthiness experiments and analysis of annotation guidelines (LRQ4). |
| P4 | Ni et al. (2024). *AFaCTA: Assisting the Annotation of Factual Claim Detection with Reliable LLM Annotators*. ACL, 1890–1912. https://aclanthology.org/2024.acl-long.104/ | Exclude from main extraction; retain as background | Factual claim detection is not equivalent to prioritizing claims for fact-checking. Under a strict reading of I1, the identified factuality task alone does not establish eligibility. |
| P5 | Wang et al. (2024). *Factcheck-Bench: Fine-Grained Evaluation Benchmark for Automatic Fact-checkers*. Findings of EMNLP, 14199–14230. https://aclanthology.org/2024.findings-emnlp.830/ | Include | Although the benchmark covers a broader pipeline, it explicitly evaluates check-worthiness as a separate subtask. Relevant to LRQ4. |
| P6 | Nenno (2024). *Is checkworthiness generalizable? Evaluating task and domain generalization of datasets for claim detection*. Neural Computing and Applications, 36, 15165–15176. https://doi.org/10.1007/s00521-024-09896-4 | Include | Direct cross-dataset evaluation without further training on the target dataset (LRQ1 and LRQ4). |
| P7 | Du, Gollapalli and Ng (2022). *NUS-IDS at CheckThat! 2022: Identifying Check-worthiness of Tweets using CheckthaT5*. CLEF Working Notes, CEUR 3180. https://ceur-ws.org/Vol-3180/paper-36.pdf | Include | Tweet check-worthiness with an explicit URL-treatment comparison (LRQ3 and LRQ4). |
| P8 | Zhou, Wu and Fung (2021). *Fight for 4230 at CheckThat! 2021: Domain-Specific Preprocessing and Pretrained Model for Ranking Claims by Check-Worthiness*. CLEF Working Notes, CEUR 2936. https://ceur-ws.org/Vol-2936/paper-57.pdf | Include | Evaluates a preprocessing pipeline and pretrained models for check-worthiness ranking (LRQ3 and LRQ4). |
| P9 | Carik and Yeniterzi (2021). *SU-NLP at CheckThat! 2021: Check-Worthiness of Turkish Tweets*. CLEF Working Notes, CEUR 2936. https://ceur-ws.org/Vol-2936/paper-37.pdf | Include | Includes a URL-expansion comparison. Turkish evidence is relevant methodologically but must not be presented as an English result (LRQ3 and LRQ4). |
| P10 | Hyben et al. (2026). *MultiCW: A Large-Scale Balanced Benchmark Dataset for Training Robust Check-Worthiness Detection Models*. Findings of EACL, 3737–3754. https://aclanthology.org/2026.findings-eacl.194/ | Include | Multilingual check-worthiness benchmark with out-of-distribution evaluation (LRQ1 and LRQ4). |
| P11 | Hyben et al. (2024 revision). *Multilingual and Multi-topical Benchmark of Fine-tuned Language Models and Large Language Models for Check-Worthy Claim Detection*. arXiv:2311.06121. https://arxiv.org/abs/2311.06121 | Include | Its relationship to P10 requires a version and dataset comparison. No separate quantitative contribution is used here, and a duplicate relationship is not asserted as verified. |
| P12 | Vykopal, Ostermann and Šimko (2025). *Soft Language Prompts for Language Transfer*. NAACL, 10294–10313. https://aclanthology.org/2025.naacl-long.517/ | Include | Includes check-worthiness among its evaluated tasks. Language transfer provides related evidence, not a direct test of debate-to-Twitter transfer (LRQ1 and LRQ4). |
| P13 | Li, Panchendrarajan and Zubiaga (2024). *FactFinders at CheckThat! 2024: Refining Check-worthy Statement Detection with LLMs through Data Pruning*. CLEF Working Notes, CEUR 3740. https://ceur-ws.org/Vol-3740/paper-47.pdf | Include | Examines training-data pruning. Relevant to LRQ2, but changing data quality and quantity together does not isolate training-set size. |

### Screening disagreement: P11

**AI recommendation:** Exclude P11 because potential overlap with P10 .

**Group decision:** Include P11 because it addresses relevant review questions.

**Resolution:** Retain both publications. Record their results separately, but do not treat potentially overlapping datasets or experiments as independent evidence. The relationship between P10 and P11 remains unverified.

## 3. Data and methods

| ID | Objective and strategy | Data and annotation | Models, training and preprocessing |
|---|---|---|---|
| P1 | Build a check-worthiness ranking system. | Political debates; English and Arabic. Labels derive from claims selected by nine fact-checking organizations. Evaluation uses five debates for training and two for testing. Exact sentence counts and class distribution: not verified. | Feed-forward neural network with word embeddings and linguistic features. English/Arabic tokenization and Arabic segmentation are described. This is not a controlled normalization experiment. |
| P2 | Handle unlabeled positive examples and transfer learned representations. | Wikipedia source data; PHEME tweets and political statements as target tasks. PHEME contains 5,802 tweets, including 1,972 rumours. Label definitions differ across datasets. | BERT with positive-unlabelled learning and positive-unlabelled conversion. Target-domain training is used. PHEME uses leave-one-event-out evaluation. Specific URL and punctuation treatment: not verified. |
| P3 | Test whether LLMs follow annotation guidelines. | ClaimBuster, CLEF 2022, EnvironmentalClaims, NewsClaims and PoliClaim. Evaluated sample sizes: 1,032; 251; 275; 1,622; and 816 respectively. | GPT-3.5, GPT-4 and Llama 3 8B Instruct; prompts vary guideline detail and examples. SVM and fine-tuned BERT provide comparisons. LLM experiments use one run per model/prompt setting. |
| P5 | Evaluate individual stages of automatic fact-checking. | 94 generated responses; 678 atomic claims, including 661 check-worthy claims, 16 opinions and one non-claim. Independent annotation is followed by consolidation. | Includes a zero-shot ChatGPT check-worthiness baseline. Claim decomposition and decontextualization belong to the broader pipeline. No target-training-size experiment. |
| P6 | Measure task and domain generalization. | Multiple English claim-detection datasets, including ClaimBuster and CheckThat! collections. Dataset definitions and label policies differ. | BERT, RoBERTa, BLOOM and conventional classifiers. Models trained on a source dataset are evaluated on other datasets without further target training. Repeated source splits are used. |
| P7 | Classify multilingual tweets for check-worthiness. | CheckThat! 2022 tweets in six languages. English training set: 2,122 tweets, including 447 positives. | CheckthaT5 uses mT5-XL. Experiments include class balancing and replacing URLs with `[LINK]`. The selected checkpoint is based on development performance. |
| P8 | Improve check-worthiness ranking through domain-specific processing. | CheckThat! 2021 English tweets and political speech data. Exact split sizes and class distributions: not verified in this extraction. | BERTweet and other pretrained models. Processing includes link removal, punctuation normalization, contraction handling and expansion of abbreviated numbers. These changes form a combined pipeline. |
| P9 | Rank Turkish tweets by check-worthiness. | CheckThat! 2021 Turkish tweets. Exact split sizes and class distribution: not verified in this extraction. | Turkish BERT and multilingual comparisons. Mentions are normalized; hashtags and emojis are removed. URL expansion is compared with the alternative URL treatment. |
| P10 | Build and evaluate a broad check-worthiness benchmark. | Main dataset pool: 123,722 examples across 16 languages; out-of-distribution pool: 27,761 examples. Includes different topics and text styles. | Fine-tuned multilingual classifiers and zero-shot LLMs. Reported fine-tuning results include three runs. Treatment of related translated examples across splits needs further checking. |
| P11 | Benchmark fine-tuned language models and zero-shot LLMs for multilingual check-worthiness detection. | The composite General Claim dataset combines five public corpora and contains 420,738 samples across 10 languages and six topics (Table 2). NewsClaims and ClaimBuster are held out for cross-corpus evaluation. | Fine-tunes mDeBERTa, XLM-RoBERTa and LESA. Compares them with zero-shot GPT-3.5, GPT-4, Alpaca-LoRA and Mistral-7B. Also evaluates performance with and without a bundle of preprocessing steps. |
| P12 | Improve cross-language transfer using soft language prompts. | Four tasks, including check-worthiness, across high- and low-resource languages. Task-specific sizes and class distributions: not verified here. | mT0-base with parameter-efficient adaptation and language prompts. Unlabelled language data are used. Check-worthiness experiments are not a target-label learning curve. |
| P13 | Improve classification by removing problematic training examples. | English political statements. Compared training-set sizes include 22,499; 20,141; 10,227; and 9,907 examples. | Llama 2 7B with LoRA, prompt comparisons and two-stage data pruning. Pruned subsets differ in composition and quality as well as size. |

## 4. Results and supporting locations

Metric values are kept in their original evaluation context. They must not be compared across papers as if they used the same test set or label definitions.

| ID | Extracted finding | Supporting location | Interpretation and limitation |
|---|---|---|---|
| P1 | The English word2vec configuration reports MAP = 0.323. | §§3.2–3.5; Table 1, p. 29. | Ranking evidence on political debates. It does not establish performance on Twitter. |
| P2 | Transferred BERT + PUC reports mean positive-class rumour F1 = 61.1 ± 1.9% on PHEME. | Experimental setup; Table 2, p. 482. | Target training is present. The reported mean and variation must not be labelled zero-shot performance. |
| P3 | For GPT-4 on CLEF check-worthiness, positive-class F1 changes from 0.467 with V0 to 0.583 with V2. | Table 3, p. 250; Appendix B for model settings. | Shows sensitivity to guideline prompting. It does not isolate preprocessing or training-set size. |
| P5 | Check-worthiness baseline: accuracy = 0.932, macro-F1 = 0.319. Always predicting check-worthy gives accuracy = 0.975, macro-F1 = 0.329. | §4.2, Table 3, p. 14206. | Strong class imbalance makes accuracy alone misleading. Generated responses are a different domain from tweets. |
| P6 | Cross-dataset performance frequently deteriorates relative to within-dataset evaluation. | §3.1; Table 3; discussion and appendix. | Direct support for investigating generalization. Domain shift and annotation-policy differences are intertwined. |
| P7 | English positive-class F1 increases from 0.643 with links to 0.682 with `[LINK]` replacement in the reported development comparison. Dutch performance decreases slightly. | Table 2 and associated preprocessing discussion. | URL treatment is language- and setting-dependent. These development results are not the official final-test score. |
| P8 | In the reported k-fold comparison, BERTweet MAP changes from 0.8332 to 0.8370 with preprocessing. | Table 4; §3.2 for processing steps. | A bundled preprocessing comparison cannot identify the contribution of each individual operation. |
| P9 | Average MAP changes from 0.662 without URL expansion to 0.684 with expansion. | §4.1 and §5. | The comparison uses five models. It concerns Turkish tweets; English generalization is untested by this result. |
| P10 | mDeBERTa accuracy is 0.923 within distribution and 0.866 out of distribution. | Tables 6–7. | Supports separate reporting of within- and out-of-distribution evaluation. It is not a controlled test of the group's exact transfer setting. |
| P11 | mDeBERTa usually achieved the highest positive-class F1 among the fine-tuned models. The best fine-tuned models performed slightly better than the best zero-shot LLMs in the multilingual comparison. | §§7.1–7.2 and 8, Figures 2–8. | Related evidence for cross-corpus generalization (LRQ1).
| P12 | Check-worthiness is explicitly evaluated within the language-transfer experiments. | Experimental setup; Appendix, Table 7. | Cross-language evidence is relevant background. The exact F1 averaging convention was not verified, so no numerical F1 comparison is extracted here. |
| P13 | Reported test F1 changes from 0.820 ± 0.019 without pruning to 0.831 ± 0.009 with both pruning steps. | Tables 8–9; §3.6. | This does not establish that fewer labels alone improve performance. The reported variation is not assumed to represent independent retraining seeds. |

## 5. Quality appraisal under protocol §9

All included papers state an identifiable objective and use empirical methods relevant to at least one LRQ. The main concerns are recorded below.

| ID | Data and labels | Controlled comparisons | Training/evaluation separation | Uncertainty and limitations |
|---|---|---|---|---|
| P1 | Debate sources and organizational labels described; some counts not verified. | Model configurations compared. | Five training debates and two test debates identified; validation details not verified. | Repeated-run uncertainty not established by this extraction; narrow domain. |
| P2 | Source and target labels described, but their meanings differ. | PN, PU and PUC comparisons. | Target folds and validation procedure described. | Multiple seeds and variation reported; not zero-shot transfer. |
| P3 | Multiple datasets and annotation schemes described. | Prompt variants compared; baseline test-set comparability requires care. | Dataset sampling described. | One LLM run per setting; contamination and dataset differences discussed. |
| P5 | Annotation procedure and label imbalance described. | Includes an always-positive baseline. | Zero-shot baseline; no target training evaluated. | Small, highly imbalanced benchmark; repeated-run uncertainty not established here. |
| P6 | Dataset definitions and differences described. | Multiple models and source/target combinations. | No further target training in cross-dataset evaluation; tuning separation needs further checking. | Repeated splits; domain and task-definition shifts are confounded. |
| P7 | Dataset counts and label balance described. | URL replacement explicitly compared. | Development-based checkpoint selection; development and official-test results separated here. | Repeated-run uncertainty for the URL comparison not verified. |
| P8 | Shared-task data identified; some details not extracted. | Preprocessing bundle compared with its absence. | K-fold and official evaluation are distinct. | Individual processing effects are not isolated; folds are not equivalent to independent training seeds. |
| P9 | Shared-task data and processing described. | URL expansion explicitly compared. | Exact split details need checking. | Multi-model averages reported; evidence is language-specific. |
| P10 | Large multilingual benchmark described. | Model families and evaluation conditions compared. | Out-of-distribution evaluation identified; translation-related leakage control needs checking. | Three runs reported; rounded variation should not be interpreted as zero uncertainty. |
| P11 | Source corpora, sample counts and split sizes are documented. The composite dataset combines sources with different annotation schemes. | Compares model families and evaluates the full preprocessing bundle with and without it. The effect of each preprocessing step is unresolved. | Describes train, validation and test splits. NewsClaims and ClaimBuster are held out from fine-tuning for cross-corpus evaluation. | One run per configuration limits assessment of run-to-run variability. |
| P12 | Multiple tasks and languages described. | Adaptation methods compared. | Validation-based selection described. | Check-worthiness replication across seeds not established; language transfer differs from corpus transfer. |
| P13 | Pruned subset sizes reported. | Pruning configurations compared. | Development and test results reported separately. | Size and quality effects are confounded; meaning of repeated-run variation needs checking. |

## 6. Search extension and citation tracing

The review was extended beyond the original five-paper pilot.

- Access method: general web search and direct primary-source pages/PDFs.
- Native database searches are not claimed.
- Additional records P6–P13 were inspected.
- The detailed search queries, access attempts and candidate queue are recorded in `search-extension.md`.
- ACM and IEEE access limitations prevented complete native-source coverage.
- No exhaustive Google Scholar search or reliable total result count is claimed.

Verified citation links include:

| Direction | Citation link | Handling |
|---|---|---|
| Backward | P3 cites work associated with Hyben et al., arXiv:2311.06121. | The available revision is recorded as P11; title/version differences require care. |
| Forward | P12 cites Hyben et al., arXiv:2311.06121. | P12 was screened and included because its experiments contain a check-worthiness task. |

These links document a limited citation-tracing extension. They do not demonstrate exhaustive backward or forward snowballing.

## 7. Findings relevant to the research questions

### LRQ1 — Cross-corpus transfer

P6 provides direct evidence for evaluating models on new datasets without target training. P10 adds out-of-distribution evidence.

P2 uses target training, while P12 investigates language transfer. They must not be presented as direct tests of the group's zero-shot debate-to-Twitter setting.

### LRQ2 — Labeled target-domain training size

P13 provides related evidence about training-data selection, but pruning changes both quantity and quality.

The extracted studies do not establish the proposed learning curve for 50, 100, 250 and 500 randomly selected target-domain labels.

### LRQ3 — Preprocessing

P7 and P9 provide explicit URL-treatment comparisons. P8 evaluates a broader processing pipeline.

The findings do not support a universal rule to remove all URLs, numbers or punctuation. Each operation should be distinguished in the planned comparison.

### LRQ4 — Datasets and evaluation

P1, P3 and P5 illustrate differences in task definitions and labels. P5 particularly demonstrates why accuracy alone can mislead under class imbalance.

Ranking MAP, positive-class F1, macro-F1 and accuracy must remain separate. Development results must not be substituted for final-test results.

## 8. Human check

The review made the following decisions:

1. Retained P5 because it contains an explicit check-worthiness subtask.
2. Excluded P4 from the main extraction under the strict task criterion.
3. Include P11 because it addresses relevant review questions.
4. Marked unestablished details as “Not verified” instead of inventing values.
