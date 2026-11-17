 Floor 3 — Research Strategy Decision Table

Status: APPROVED BY THE GROUP — strategy selection approved; feasibility checks remain open.
Source: Meeting 3.
Research context: Check-Worthiness Detection; see `research-plan/rq-and-hypotheses.md`.

Decision criteria
- Classify the question first: exploratory, frequency/process, relationship, causality, or design (design is not a knowledge question).
- Compare intervention (how much researchers manipulate the setting) and generalization (how far findings extend beyond the case).
- Weigh three competing aims: A = generalization across actors; B = precision/control of behavior; C = realism of context.
- Distinguish inherent limitations (cannot be removed without changing strategy) from fixable execution problems.
- Evaluate feasibility: dataset access, time, ethics/privacy, annotation capacity, computing resources.
- Choose strategy before method, then data collection.

Eight-strategy reference table
| Strategy | Environment | Suitable question types / situations | Gains | Inherent cost | Feasibility for our project |
|---|---|---|---|---|---|
| Field Study | Natural | Exploratory or process questions about actual fact-checking workflows without intervention | C: realism | Limited statistical generalization and measurement precision | Low unless access to fact-checking teams |
| Field Experiment | Natural | Causal/evaluation questions when introducing a tool into real fact-checking work | Realism plus some intervention | Confounding and limited transfer to other organizations | Low unless partner organization available |
| Experimental Simulation | Designed | Causal/process questions in a staged but realistic fact-checking task | Behavioral control with some realism | Artificial context; generalization restricted to simulated setting | Medium if recruiting participants |
| Laboratory Experiment | Designed | Controlled comparison of ML systems, training sizes, preprocessing or evaluation conditions | B: measurement precision and experimental control | Artificial context and limited generalization beyond tested corpora/models | High if datasets, labels and compute available |
| Judgment Study | Neutral | Expert judgments on check-worthiness criteria or model output quality | Generalization across elicited expert opinions | Selected experts and lack of natural context | Medium/low if experts unavailable |
| Sample Study | Neutral | Frequency, prevalence or association in a sampled population of posts/repositories | A: generalization across sampled actors, with representative sampling | Less control and contextual detail | Medium if sampling frame and labels exist |
| Formal Theory | Non-empirical | Conceptual explanation or formal propositions built from prior research | Broad conceptual scope | No new empirical observations | Medium for conceptual work; not sufficient alone to test F1 hypotheses |
| Computer Simulation | Non-empirical | Scenario exploration using a computational model of posting or fact-checking behavior | Many scenarios at low marginal cost | Findings depend on model assumptions; no new observed behavior | Medium if a valid simulation model is defined |

 Group-approved strategies for our three research questions

| RQ | Research question type | Proposed primary strategy | Why this fits | Inherent limitation | Alternative to consider | Group decision |
|---|---|---|---|---|---|---|
| RQ1: Zero-shot transfer from CheckThat! debates to Twitter | Comparative/relationship (knowledge) | Laboratory Experiment | Fixed trained BERT checkpoint and matched evaluation conditions allow controlled F1 comparison between corpora | Results may not generalize to other languages, datasets, annotation schemes or models; corpus differences may remain | Sample Study for broader corpus-level observational generalization | Approved: Laboratory Experiment |
| RQ2: Target-domain fine-tuning set size vs F1 | Relationship (knowledge; associational wording in current RQ) | Laboratory Experiment | Vary labeled training sample size across 50/100/250/500 while holding model/test set and other conditions constant | Results specific to selected architecture, tweet pool, and training setup | Sample Study for observational association across existing model runs | Approved: Laboratory Experiment |
| RQ3: Text normalization vs unmasked syntax | Comparative (knowledge) | Laboratory Experiment | Change preprocessing pipeline while keeping model architecture, training split, evaluation set and hyperparameters fixed | May not generalize to other corpora, languages or architectures | Experimental Simulation only if a staged human workflow is studied instead | Approved: Laboratory Experiment |

Feasibility constraints to verify before implementation
- Confirm that 1,000 English tweets can legally and ethically be collected, anonymized and annotated by two coders.
- Confirm access and licensing for CheckThat! 2024 Task 1 data and annotation guidelines.
- Confirm compute/time budget for BERT fine-tuning, 5 seeds, and bootstrap analyses.
- Confirm how the 25% class-prevalence matching in RQ1 will be implemented without data leakage.
- Confirm group members accept the limited generalizability of controlled laboratory evaluation.

Group's independent decision and rationale
Decision status: The group has approved Laboratory Experiment as the primary strategy for RQ1, RQ2 and RQ3. The justifications and trade-offs are recorded above. Feasibility constraints listed above still require verification.


