# Floor 3 Test Log: Research Strategy Evaluation (RQ1–RQ3)

**Date:** 2026-11-18
**Inputs:** `rq-and-hypotheses.md` (authoritative RQ/hypothesis wording), `decision-table.md` (group-approved), `strategy-advisor` skill
**Status:** Provisional. The group retains Laboratory Experiment for RQ1; RQ2 and RQ3 are approved in `decision-table.md`. Feasibility checks remain open.
**Scope note:** The agent evaluated and critiqued only. No RQs, hypotheses, project files or the decision table were modified. Claims that could not be verified from the supplied files are marked [UNVERIFIED].

---

## 1. Strategies recommended (conditional)

| RQ | Preferred (conditional) | Compared alternatives | Key assumptions |
|:--|:--|:--|:--|
| RQ1 | Laboratory Experiment | Sample Study (conflicts with 25% prevalence matching); Judgment Study (supporting only, for label equivalence); Computer Simulation (variance/power planning only) | Comparable labels, documented stratification, adequate positives, unpaired comparison across different test sets |
| RQ2 | Laboratory Experiment | Sample Study (loses control, no existing runs listed); Computer Simulation (supplement only) | Stated training-budget policy, clean validation data, explicit seed and subset procedure |
| RQ3 | Laboratory Experiment | Sample Study (descriptive complement); Experimental Simulation (weak unless the question shifts to a human workflow) | Unambiguous pipeline specification, one named primary test, stated seed pairing, anonymized retained URLs |

---

## 2. Agreements and disagreements with the group's decisions

**Agreement**
- Conditional agreement with Laboratory Experiment for all three RQs. It fits a controlled comparison of a fixed model, with the strongest fit for RQ2 and RQ3, where the researchers manipulate the factor.

**Disagreement**
- No disagreement with the approved strategy for any RQ. The disagreements concern execution and analysis details:
  - **RQ1:** the paired bootstrap named in the Base Architecture is inappropriate across two different test sets.
  - **RQ2:** the "association" wording understates what a manipulated-N design supports, and H1.2 tests only the endpoints. Whether to keep the wording is the group's decision.
  - **RQ3:** McNemar's is listed alongside a paired bootstrap with no primary test named, and Pipeline A combines three changes.
- None of the evaluations changed the group's approved strategies.

---

## 3. Main unresolved methodological issues

- **Structural:** corpus (RQ1) and sample-pool (RQ2, RQ3) confounding and narrow scope, including a composite Pipeline A in RQ3.
- **Statistical:** about 125 test positives, no minimum effect of interest in H1.1, H1.2 or H1.3, no policy for seed aggregation, and no multiplicity or test-reuse policy across the three RQs.
- **Design gaps:** undocumented stratification of the official debate test set, unspecified threshold and preprocessing policy, undefined training budget across N levels, and no target-domain validation split.
- **Label validity:** no cross-corpus label-equivalence check or adjudication rule (RQ1).
- **Privacy:** confirm that URLs retained in RQ3 Pipeline B cannot identify individuals.
- **Sources:** Nenno 2024, Meng et al. 2024 and Hasanain et al. 2024 are unverifiable from the supplied files [UNVERIFIED].

---

## 4. Consolidated issues table

Statuses reflect the uploaded `rq-and-hypotheses.md` and `decision-table.md` as last read. "Recommendation" is what was raised in the evaluations; no new solutions were added.

| RQ | Methodological issue or disagreement | Your recommendation | Status |
|:--|:--|:--|:--|
| RQ1 | Strategy: Laboratory Experiment (approved) versus Sample Study and Judgment Study | Conditional agreement. It holds if labels are comparable, stratification is documented, positives are adequate and the comparison is unpaired. Sample Study conflicts with the 25% matching | Partially addressed (feasibility checks still open) |
| RQ1 | Domain confounding: genre bundles platform, length, register, topic and annotators (structural) | Interpret the result as a corpus comparison, not a causal claim about formality | Unresolved |
| RQ1 | Label equivalence: same guidelines and a κ ≥ 0.70 target do not show tweet labels match the official debate labels, and there is no adjudication rule | Report IAA on tweets. Consider a cross-corpus check, and specify the adjudication rule | Partially addressed |
| RQ1 | About 125 positives per corpus, and the debate test set size after stratification is unknown | Verify the post-stratification size and report bootstrap CIs | Unresolved |
| RQ1 | Stratification of the "official" debate test set is undocumented, with leakage handling open | Document the stratification procedure | Unresolved |
| RQ1 | Decision threshold and calibration policy are unstated, so an F1 drop could reflect threshold shift | State the threshold policy and what the design can detect | Unresolved |
| RQ1 | Preprocessing across debates and tweets is unspecified for RQ1 | Use identical, documented preprocessing | Partially addressed (`@user` anonymization noted) |
| RQ1 | Paired bootstrap is inappropriate across different test sets, and seed variance is not integrated into the inference | Use an unpaired comparison for different items, and specify how seeds enter | Unresolved |
| RQ1 | H1.1 has no minimum effect of interest (p < 0.05 only) | The group must decide on a minimum meaningful effect | Unresolved |
| RQ1 | The RQ asks how F1 "changes" (non-directional), while H1.1 is directional | Justify the direction within RQ1. The cited theory is unverifiable [UNVERIFIED] | Unresolved |
| RQ1 | Single-run variance | The 5 seeds help. Aggregation with item resampling still needs specifying | Partially addressed |
| RQ1 | Language and scope: the English subset is named, but details cannot be verified from the supplied files [UNVERIFIED] | Confirm the subset details against the source | Partially addressed |
| RQ2 | Strategy: Laboratory Experiment (approved) versus Sample Study and Computer Simulation | Conditional agreement. It is the best fit for a manipulated N, provided a budget policy, clean validation and a seed and subset procedure exist. Sample Study loses control, and Computer Simulation is only a supplement | Partially addressed (feasibility checks still open) |
| RQ2 | H1.2 tests only N = 50 versus N = 500, so intermediate levels and the shape of the association are untested | The group must decide whether levels 100 and 250 enter the inference | Unresolved |
| RQ2 | N = 500 uses the entire pool, so its training data cannot vary across seeds, and the nested subsets are not independent | State the seed and subset procedure | Unresolved |
| RQ2 | Few positives at N = 50 (about 12 to 13 if the pool is 25% positive [UNVERIFIED]), so rounding and stability matter | Specify rounding and verify the pool prevalence | Unresolved |
| RQ2 | Training budget is confounded with N if epochs are fixed (identical hyperparameters) | State the budget policy (epochs versus steps) | Unresolved |
| RQ2 | No target-domain validation split, so the test set could leak through model selection | Define validation data so the test set stays untouched | Unresolved |
| RQ2 | The paired bootstrap suits the design, but it captures only test-item variability, and seed handling in the p-value is unspecified | Specify how seeds enter the p-value | Partially addressed |
| RQ2 | H1.2 has no minimum effect of interest | The group must decide on a minimum meaningful effect | Unresolved |
| RQ2 | The RQ says "association", but N is manipulated, so wording understates the inference the design supports | I did not change it. Whether to keep it is the group's decision | Unresolved |
| RQ2 | Results are specific to one pool, model and setup (structural) | Acknowledge the limited scope | Unresolved |
| RQ3 | Strategy: Laboratory Experiment (approved) versus Sample Study and Experimental Simulation | Conditional agreement. It is the best fit and the most feasible, assuming an unambiguous pipeline specification, one named primary test, a stated seed pairing and anonymized URLs. Experimental Simulation is weak unless the question shifts to a human workflow | Partially addressed (feasibility checks still open) |
| RQ3 | Pipeline A is a composite of three changes (number masking, URL removal, punctuation removal), so effects cannot be attributed to any one (structural) | The group must say whether the composite manipulation is intended | Unresolved |
| RQ3 | The pipeline definition is inconsistent within the file (URL handling and punctuation) | Specify both pipelines unambiguously | Unresolved |
| RQ3 | The file lists McNemar's and a paired bootstrap, without naming a primary test. McNemar's does not directly test an F1 difference | Name the primary test. A paired bootstrap on F1 matches the DV | Unresolved |
| RQ3 | The paired design is appropriate (same test items), but seed pairing and aggregation are unspecified | Specify seed pairing and aggregation | Partially addressed |
| RQ3 | Pipeline B retains URL tokens, which could expose identifying information, and only `@user` anonymization is stated | Confirm retained URLs cannot identify individuals | Unresolved |
| RQ3 | The mechanism is not guaranteed (a `<number>` placeholder still signals a number, and raw tokens could add noise at N = 500). The theoretical support is unverifiable [UNVERIFIED] | Flagged only. The direction rests on unverified theory | Unresolved |
| RQ3 | Low power for plausibly small effects, and no minimum effect of interest | The group must decide on a minimum meaningful effect | Unresolved |
| RQ3 | "Identical checkpoint" is ambiguous (the same starting checkpoint, or the CheckThat!-initialized one used in RQ1 and RQ2) | Clarify the intended meaning | Unresolved |
| RQ3 | No validation split is described, so the test could leak through pipeline tuning | Define validation data so the test set stays untouched | Unresolved |
| RQ3 | The effect is tested at N = 500 only, so interaction with sample size is untested (structural) | Acknowledge the limited scope | Unresolved |
| RQ1–RQ3 | The same 500 test tweets are reused with α = 0.05 per hypothesis, and no multiplicity or test-reuse policy is stated | The group must decide on a policy | Unresolved |
| RQ1–RQ3 | The cited sources (Nenno 2024; Meng et al. 2024; Hasanain et al. 2024) cannot be verified from the supplied files [UNVERIFIED] | Verify against the actual sources | Unresolved |
| RQ1–RQ3 | Preprocessing is unspecified for RQ1 and RQ2, which may link them to the RQ3 pipelines | Specify the preprocessing used in each RQ | Unresolved |

**Notes**
- No RQ has a "Resolved" status, because the group has not reported changes to the files. Mapping earlier "addressed in design" wording to "Partially addressed" is a judgment call.
- This log records evaluation results only. Whether any acceptance test passes or fails must be recorded separately, based on the actual prompt and output.
