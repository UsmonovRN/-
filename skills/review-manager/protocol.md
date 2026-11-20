# Literature Review Protocol

## 1. Topic and Purpose

This review examines automatic check-worthiness detection,
with a focus on transferring models between corpora,
adapting models to Twitter/X data, and evaluating text
preprocessing choices.

The purpose is to identify empirical evidence that supports,
challenges, or limits the assumptions behind the group's
existing research questions:

- RQ1: Zero-shot transfer from the source corpus to Twitter.
- RQ2: Target-domain fine-tuning sample size and detection quality.
- RQ3: Text normalization versus preservation of surface features.

The review will inform the planned laboratory experiments.
It will not change the group's research questions, hypotheses,
or approved research strategy automatically.

Descriptions of datasets and findings already mentioned in
the research plan must be verified against original sources.
Their presence in the repository does not establish accuracy.

## 2. Literature Review Questions

### LRQ1: Cross-Corpus Transfer — Supports RQ1

What empirical evidence describes changes in check-worthiness
detection performance when models are evaluated on a different
corpus or domain without target-domain fine-tuning?

Extract information about:
- Source and target corpora.
- Languages, topics, and text genres.
- Annotation definitions and class distributions.
- Models, evaluation metrics, and transfer results.
- Explanations and limitations reported by the authors.

### LRQ2: Target-Domain Adaptation — Supports RQ2

How do existing studies evaluate the relationship between
the amount of labeled target-domain training data and
check-worthiness detection performance?

Extract information about:
- Fine-tuning sample sizes.
- Sampling and class-balancing procedures.
- Initial model and adaptation method.
- Training, validation, and test separation.
- Repeated runs, learning curves, and uncertainty estimates.

### LRQ3: Text Preprocessing — Supports RQ3

What empirical evidence shows how preprocessing choices affect
check-worthiness detection, particularly the treatment of
numbers, URLs, punctuation, and other social-media features?

Extract information about:
- Features removed, masked, normalized, or preserved.
- Whether preprocessing is applied during training and testing.
- Whether comparisons control other experimental conditions.
- Reported effects on performance and their limitations.

### LRQ4: Data and Evaluation — Supports RQ1–RQ3

Which datasets, annotation procedures, and evaluation practices
are suitable for interpreting and planning the comparisons
in RQ1–RQ3?

Extract information about:
- Task definitions and annotation guidelines.
- Dataset composition and access conditions.
- Annotator agreement.
- Evaluation metrics and positive-class definitions.
- Data leakage controls and statistical comparisons.

These are literature review questions. They do not replace
the research questions in research-plan/rq-and-hypotheses.md.

## 3. Search Strings

Use the following search strings as starting queries.
Adapt syntax to each search platform and record the exact
query that was actually executed.

### Q1: General Check-Worthiness Literature

("check-worthiness" OR "check worthiness" OR "checkworthy"
OR "claim worthiness")
AND
(detection OR classification OR ranking)

### Q2: Cross-Corpus Transfer

("check-worthiness" OR "check worthiness" OR "checkworthy")
AND
("cross-domain" OR "cross-dataset" OR "cross-corpus"
OR "domain generalization" OR "domain adaptation"
OR "transfer learning" OR "zero-shot")

### Q3: Target-Domain Fine-Tuning

("check-worthiness" OR "check worthiness" OR "checkworthy")
AND
("fine-tuning" OR "fine tuning" OR "few-shot"
OR "training size" OR "sample size"
OR "learning curve" OR "limited labeled data")

### Q4: Preprocessing

("check-worthiness" OR "check worthiness" OR "checkworthy")
AND
(preprocessing OR normalization OR masking OR tokenization
OR numbers OR URLs OR punctuation)

### Q5: Social Media and Datasets

("check-worthiness" OR "check worthiness" OR "checkworthy"
OR "CheckThat")
AND
(Twitter OR tweets OR "social media"
OR dataset OR annotation OR benchmark)

If a focused query returns too few relevant results,
use Q1 and screen the retrieved papers for the relevant
review question. Record any query revision and its reason.

Do not search only for findings that support the hypotheses.

## 4. Search Sources and Scope

### Main Search Sources

- ACL Anthology.
- ACM Digital Library.
- IEEE Xplore.

### Supplementary Search Sources

- Google Scholar for discovery and citation tracing.
- CEUR-WS and official CheckThat!/CLEF task pages for
  task descriptions, proceedings, and dataset documentation.
- arXiv for supplementary preprints.

### Search Scope

- Search titles, abstracts, and keywords where supported.
- Include English-language full texts.
- Apply no initial lower publication-year limit.
- Search up to the actual date of each search.
- Record unavailable databases and access restrictions.
- Do not claim to have searched a database that was inaccessible.

For Google Scholar, screen the first 100 results per query
under relevance sorting, or all results if fewer are returned.
Record this limit as a coverage limitation.

For other sources, screen all retrieved results where feasible.
If the result set is too large, document and agree on a query
refinement before screening.

Identify preprints separately from peer-reviewed publications.
When multiple versions report the same study, retain the final
published version as the main record when available and link
any supplementary version.

## 5. Inclusion Criteria

Include a source when all applicable conditions are met:

I1. It directly concerns check-worthiness detection,
claim prioritization for fact-checking, or documentation
of a dataset used for that task.

I2. It contributes information to at least one review question:
transfer, adaptation, preprocessing, data, or evaluation.

I3. It provides empirical methods and results, a relevant
literature review, or official task/dataset documentation.

I4. Its full text is available for assessment.

I5. Its bibliographic identity can be verified.

I6. Its English-language text provides enough detail to
extract the information relevant to the review.

Assign each included source an evidence category:
- Primary empirical study.
- Review or background source.
- Official task or dataset documentation.
- Preprint.

Use primary empirical studies to support claims about
measured performance. Do not treat documentation or
background discussion as experimental evidence.

## 6. Exclusion Criteria

Exclude a source if any of the following applies:

E1. It concerns only claim truth verification, evidence retrieval,
fake-news detection, sentiment analysis, or account behavior,
without a relevant check-worthiness component.

E2. It is a duplicate report of an already recorded study,
unless it provides additional relevant information.

E3. It is an opinion piece, promotional page, or unsupported
summary without usable research or dataset information.

E4. It does not address any literature review question.

E5. Its full text cannot be obtained. Record it as
"Full text unavailable"; do not describe this as proof
that the source does not exist.

E6. Its identity remains unverified after documented checks.
Keep it in the verification log and exclude it from
the verified evidence synthesis.

Do not exclude a study because its findings contradict
the group's hypotheses or report no improvement.

## 7. Search and Screening Procedure

1. Record the protocol version before starting the search.

2. Execute the search strings and create a search log:
   date, source, exact query, filters, result count,
   screening limit, and access restrictions.

3. Combine results and remove duplicates using DOI,
   normalized title, authors, and publication year.

4. Screen titles and abstracts against the inclusion
   and exclusion criteria.

5. Read the full text before final inclusion.

6. Record a decision for every full-text candidate:
   Include, Exclude, or Pending.

7. Record the criterion and reason for every exclusion.

8. Have a second group member independently screen
   a fixed sample of 20 candidates, or all candidates
   if fewer than 20 are available.

9. Compare decisions, discuss disagreements, and record
   their resolution.

10. Perform backward and forward snowballing from
    included relevant studies.

11. Apply the same criteria to sources found through
    snowballing.

12. Continue snowballing until a complete round adds
    no new eligible studies, or document a stopping
    constraint and its effect on coverage.

Keep counts for retrieved records, duplicates,
screened records, full texts, exclusions, and inclusions.

## 8. Source Verification

For each candidate source:

1. Search for the exact title.
2. Check authors, year, and publication venue.
3. Check the DOI, when assigned, and confirm that it
   resolves to the same work.
4. Open the original full text.
5. Locate the specific claim, method, or result being used.
6. Record the page, section, table, or figure supporting it.

A missing DOI does not by itself make a source invalid.
Use a stable publisher, proceedings, or institutional
record when no DOI has been assigned.

Use the verification statuses:
- Verified.
- Partially verified.
- Not verified.

For individual fields, record:
- Matches.
- Incorrect.
- Not found.
- Not applicable.

Do not fill missing details from memory.
Do not mark a source as fabricated solely because
one search failed to locate it.

### Verification Table

| ID | Reference | Title | Authors | Year | Venue | DOI or stable record | Supporting location | Verification status | Screening decision | Criterion and reason |
|---|---|---|---|---|---|---|---|---|---|---|

## 9. Data Extraction and Quality Assessment

For each included empirical study, extract:

- Full reference and verified link.
- Relevant literature review question(s).
- Study objective and research strategy.
- Source and target datasets.
- Language, domain, genre, and dataset size.
- Annotation definition and class distribution.
- Model architecture and initial checkpoint.
- Training and fine-tuning sample sizes.
- Preprocessing conditions.
- Training, validation, and test split procedures.
- Baselines and comparison conditions.
- Metrics, including the exact F1 variant.
- Number of runs and uncertainty estimates.
- Main findings and their supporting locations.
- Reported limitations.
- Relevance to RQ1, RQ2, or RQ3.

Write "Not reported" when information is absent.

Assess each study using the same questions:
- Is the research objective clear?
- Does the method fit the question?
- Are datasets and labels adequately described?
- Are comparison conditions sufficiently controlled?
- Is evaluation separated from training and tuning?
- Are uncertainty and limitations reported?

Record concerns rather than inventing missing details.
Use the assessment to qualify how strongly a study
supports a conclusion.

## 10. Evidence Synthesis

Organize findings under:
1. Cross-corpus transfer.
2. Target-domain adaptation and training sample size.
3. Text preprocessing.
4. Dataset and evaluation practices.

For each group, summarize:
- What studies agree on.
- Where findings differ.
- Which differences in methods or data may matter.
- What remains insufficiently studied.
- How the evidence informs the planned experiments.

Do not directly rank F1 values from incompatible datasets,
task definitions, class distributions, or metric variants.

Distinguish findings reported by authors from the group's
interpretation. Support every proposed research gap with
verified sources and the documented search scope.

Failure to find a study is not proof that no study exists.

## 11. Relationship to the Available Twitter/X Collection

The group reports access to approximately 450,000 posts
collected through hashtags across several topic domains.

This collection is a possible source of data for the
planned research. It is not a literature-search database
and is not assumed to have check-worthiness labels.

Its language coverage, dates, duplicates, annotation status,
and permitted use require confirmation.

The collection does not automatically replace or enlarge
the 1,000-post sample specified in the current research plan.
Any change to that plan requires a separate group decision.

## 12. Agent and Researcher Responsibilities

The review-manager agent may:
- Execute or assist with documented searches.
- Suggest screening decisions with explicit criteria.
- Check bibliographic fields against accessible sources.
- Extract information from available full texts.
- Identify missing evidence and unresolved discrepancies.

The group remains responsible for:
- Approving this protocol before using it.
- Opening and checking original sources.
- Reviewing screening decisions.
- Resolving disagreements.
- Approving interpretations and research-gap claims.

If the agent cannot access a database or full text,
it must state that limitation explicitly.

The agent must not invent references, search counts,
verification outcomes, extracted results, or test results.

Record the agent's contribution and the group's checks.
Follow the project's constitution and privacy requirements.

## 13. Outputs and Protocol Changes

Expected outputs:
- Search log.
- Screening decisions and exclusion reasons.
- Source verification table.
- Data extraction and quality-assessment table.
- Evidence synthesis linked to RQ1–RQ3.

Record protocol changes with:
- Date and version.
- Previous rule.
- Updated rule.
- Reason for the change.
- Whether earlier records require re-screening.

Do not change selection rules silently after seeing results.
