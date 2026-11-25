# Literature Search Extension

Search date: 2026-11-25
Status: Additional search and targeted citation tracing completed; review remains in progress.

## Scope and method

Protocol used: the attached protocol.md supplied on 2026-11-25. It has no version identifier; none is invented here. Inclusion rules and RQ1–RQ3 were not changed.

This continuation prioritized LRQ1 (transfer), LRQ2 (training-data quantity), and LRQ3 (preprocessing). Searches used general web-search tools, including domain-restricted queries. They were NOT native ACL Anthology, ACM DL, IEEE Xplore or Google Scholar searches.

No lower year limit was applied. Publications were considered up to the search date. English full texts were assessed. Search-engine Boolean interpretation and ranking are not controllable. Total hit counts and complete exports were unavailable. Returned batches combined results from multiple queries, so individual-query result counts cannot be reconstructed reliably.

Eight new candidate full texts were inspected at the sections relevant to eligibility and the findings below. This is a documented continuation, not an exhaustive search of every source or a completed snowballing round. Additional discovered records remain queued below.

## Exact queries executed

### Protocol queries with an ACL domain restriction

S1 — Q2:
```text
site:aclanthology.org ("check-worthiness" OR "check worthiness" OR "checkworthy") AND ("cross-domain" OR "cross-dataset" OR "cross-corpus" OR "domain generalization" OR "domain adaptation" OR "transfer learning" OR "zero-shot")
```

S2 — Q3:
```text
site:aclanthology.org ("check-worthiness" OR "check worthiness" OR "checkworthy") AND ("fine-tuning" OR "fine tuning" OR "few-shot" OR "training size" OR "sample size" OR "learning curve" OR "limited labeled data")
```

S3 — Q4:
```text
site:aclanthology.org ("check-worthiness" OR "check worthiness" OR "checkworthy") AND (preprocessing OR normalization OR masking OR tokenization OR numbers OR URLs OR punctuation)
```

### Supplementary discovery and locator queries

These narrower searches supplement, rather than replace, the protocol strings. Their purpose was to locate gap-relevant sources and resolve citations after broad results contained many directory pages and unrelated records.

| ID | Exact query | Purpose |
| --- | --- | --- |
| S4 | `"check-worthiness" "cross-domain" dataset` | Transfer evidence |
| S5 | `"check-worthiness" "training" "size" Hyben` | Adaptation and dataset-size evidence |
| S6 | `"check-worthiness" preprocessing URLs numbers` | Preprocessing evidence |
| S7 | `"Is it indeed bigger better" Hyben 2311.06121` | Resolve the Hyben citation in P3 |
| S8 | `"check-worthiness" "training size" learning curve` | LRQ2 |
| S9 | `site:dl.acm.org "check-worthiness" "sample size"` | ACM-domain discovery only |
| S10 | `site:ieeexplore.ieee.org "check-worthiness" "transfer learning"` | IEEE-domain discovery only |
| S11 | `"Claim Check-Worthiness Detection as Positive Unlabelled Learning" "training" "2025"` | Targeted forward-citation discovery from P2; limited to the year term shown |
| S12 | `"check-worthiness" "learning curve"` | LRQ2 |
| S13 | `"check-worthy" "training size"` | Supplementary terminology variant for LRQ2 |
| S14 | `"check-worthiness" "50" "100" "250"` | Locate experiments near planned sample sizes; restrictive supplementary query |

S1–S3, S7–S11 used one general web-search engine; S4–S6 and S12–S14 used a second engine for additional coverage. No query is represented as an exhaustive database search.

## Candidate register and full-text screening

IDs continue the initial P1–P5 pilot. All Include decisions are agent recommendations; independent group screening remains pending. Each included paper has an accessible English full text, identifiable authors/year/source, empirical methods and results, and a relevant check-worthiness component (I1–I6). No inclusion is based only on an abstract.

### P6 — Direct cross-corpus evidence

Sami Nenno (2024). *Is checkworthiness generalizable? Evaluating task and domain generalization of datasets for claim detection*. Neural Computing and Applications 36, 15165–15176.

- Record: https://link.springer.com/article/10.1007/s00521-024-09896-4
- PDF: https://link.springer.com/content/pdf/10.1007/s00521-024-09896-4.pdf
- DOI: 10.1007/s00521-024-09896-4
- Discovery: S4–S6 batch.
- Decision: **Include — LRQ1 and LRQ4; primary empirical study.**
- Evidence: §3.1, p. 15169 explicitly evaluates source-trained models on other corpora without further training. §4, p. 15170 and Appendix tables report cross-dataset degradation. Targets include tweet corpora.
- Interpretation: Directly relevant to RQ1, but performance losses do not isolate domain shift from differences in annotation definitions. Do not treat every target/source pairing as equivalent.
- Access: DOI redirect failed initially; publisher article and PDF opened successfully through direct links.

### P7 — URL replacement

Mingzhe Du, Sujatha Das Gollapalli and See-Kiong Ng (2022). *NUS-IDS at CheckThat!2022: Identifying Check-worthiness of Tweets using CheckthaT5*. CLEF 2022 working notes, CEUR-WS Vol. 3180.

- Full text / stable record: https://ceur-ws.org/Vol-3180/paper-36.pdf
- Discovery: S6.
- Decision: **Include — LRQ3 and LRQ4; primary empirical study.**
- Evidence: PDF p. 3, Table 2 and “Link Processing”: replace URLs with `[LINK]`. English development positive-class F1 is 0.643 with links and 0.682 with replacement. The table labels the latter condition “without links”; the paragraph explains replacement rather than deletion.
- Interpretation: Direct evidence for one preprocessing comparison in RQ3. It does not establish that every normalization step improves performance or that the difference is statistically significant. The Dutch result moves in the opposite direction.
- Table values visually checked against PDF p. 3.

### P8 — Combined tweet preprocessing

Xinrui Zhou, Bohuai Wu and Pascale Fung (2021). *Fight for 4230 at CheckThat! 2021: Domain-Specific Preprocessing and Pretrained Model for Ranking Claims by Check-Worthiness*. CLEF 2021 working notes, CEUR-WS Vol. 2936.

- Full text / stable record: https://ceur-ws.org/Vol-2936/paper-57.pdf
- Discovery: S6.
- Decision: **Include — LRQ3 and LRQ4; primary empirical study.**
- Evidence: §3.2 describes link removal, punctuation processing and expansion of quantities. §5.1.1/Table 3, PDF p. 7 compares BERTweet with its preprocessed-data variant.
- Interpretation: Relevant pipeline-level evidence, but multiple transformations are bundled. It does not identify the isolated effect of removing numbers, URLs or punctuation. Internal comparison scores must not be confused with official submission scores in Table 7.

### P9 — Preserving URL source information

Buse Carik and Reyyan Yeniterzi (2021). *SU-NLP at CheckThat! 2021: Check-Worthiness of Turkish Tweets*. CLEF 2021 working notes, CEUR-WS Vol. 2936.

- Full text / stable record: https://ceur-ws.org/Vol-2936/paper-37.pdf
- Discovery: S6.
- Decision: **Include — LRQ3 and LRQ4; primary empirical study.**
- Evidence: §4.1, PDF pp. 3–4 retains website identity through expanded URL/domain tokens. §5, PDF pp. 4–5 compares preprocessing variants with five BERTurk models each: average MAP 0.662 without URL expansion and 0.684 with expansion.
- Interpretation: Supports testing information-preserving URL treatment. Turkish tweets and MAP differ from the planned English setup and F1 evaluation; no universal advantage is inferred.

### P10 — Out-of-distribution benchmark

Martin Hyben, Sebastian Kula, Jan Cegin, Jakub Simko, Ivan Srba and Robert Moro (2026). *MultiCW: A Large-Scale Balanced Benchmark Dataset for Training Robust Check-Worthiness Detection Models*. Findings of ACL: EACL 2026, 3737–3754.

- Record: https://aclanthology.org/2026.findings-eacl.194/
- PDF: https://aclanthology.org/2026.findings-eacl.194.pdf
- DOI: 10.18653/v1/2026.findings-eacl.194
- Discovery: S1–S3; rediscovered in supplementary searches.
- Decision: **Include — LRQ1 and LRQ4; primary empirical study.**
- Evidence: §6.2/Table 7, p. 3743 evaluates fine-tuned models on a separate out-of-distribution set. Dataset and style design are described in §§3–4.
- Interpretation: Useful transfer evidence; not an exact replication of debates-to-Twitter transfer.
- Discrepancy: record abstract says six topics, PDF says seven. Use the PDF for extracted content and retain the discrepancy. Do not silently harmonize them.

### P11 — Earlier Hyben preprint

Martin Hyben, Sebastian Kula, Ivan Srba, Robert Moro and Jakub Simko (2024 revision; first submitted 2023). *Multilingual and Multi-topical Benchmark of Fine-tuned Language models and Large Language Models for Check-Worthy Claim Detection*. arXiv:2311.06121v2.

- Record: https://arxiv.org/abs/2311.06121
- PDF opened: https://arxiv.org/pdf/2311.06121
- Discovery: supplementary search; backward citation from P3, reference list p. 255.
- Decision: **Pending — relevant to LRQ1/LRQ4, but version/overlap assessment under E2 remains open.**
- Evidence: v2 abstract and experimental sections examine multilingual/cross-domain detection. P3 cites the earlier title “Is it indeed bigger better? The comprehensive study of claim detection LMs applied for disinformation tackling.”
- Version limitation: arXiv confirms first submission in 2023 and revision in 2024. Direct v1 access failed. The relation to P10 must be compared before counting independent evidence; similar authors/topic alone do not establish duplication.
- Category: Preprint; no peer-reviewed venue claimed for this version.

### P12 — Forward citation located and verified

Ivan Vykopal, Simon Ostermann and Marian Simko (2025). *Soft Language Prompts for Language Transfer*. NAACL 2025, Volume 1: Long Papers, 10294–10313.

- Record: https://aclanthology.org/2025.naacl-long.517/
- PDF: https://aclanthology.org/2025.naacl-long.517.pdf
- DOI: 10.18653/v1/2025.naacl-long.517
- Discovery: S7 returned this citing paper; reference list p. 10304 explicitly cites arXiv:2311.06121.
- Decision: **Include — LRQ1/LRQ4 methodological background; primary empirical study.**
- Evidence: §4.3/Table 1, p. 10299 includes check-worthy claim detection; §5.5, pp. 10301–10302 and Appendix Table 7 report cross-lingual transfer.
- Interpretation: Cross-language transfer is not the same as within-language corpus transfer. The paper supports methodological comparison, not a direct answer to the planned debate-to-Twitter experiment.

### P13 — Training-data quantity and selection

Yufeng Li, Rrubaa Panchendrarajan and Arkaitz Zubiaga (2024). *FactFinders at CheckThat! 2024: Refining Check-worthy Statement Detection with LLMs through Data Pruning*. CLEF 2024 working notes, CEUR-WS Vol. 3740.

- Full text / stable record: https://ceur-ws.org/Vol-3740/paper-47.pdf
- Discovery: S12–S14.
- Decision: **Include — LRQ2 and LRQ4; primary empirical study.**
- Evidence: §3.6/Table 8, PDF p. 15 compares pruning conditions; Table 9, PDF p. 16 lists 22,499 / 20,141 / 10,227 / 9,907 training examples.
- Interpretation: Relevant to the quantity/quality trade-off, but pruning changes sample selection as well as size. It is not a controlled random-subsample learning curve at 50/100/250/500 target tweets. Do not interpret it as proof that less data is always better.
- Table 8 visually checked against PDF p. 15.

## Bibliographic verification summary

“Confirmed in PDF” is a direct source check, not agreement with an independent second source. CEUR PDFs supply the title, authors, year and event; no DOI is invented. DOI resolution for ACL papers was not separately tested.

| ID | Title | Authors | Year | Venue | DOI / stable record | Status |
| --- | --- | --- | --- | --- | --- | --- |
| P6 | Matches record/PDF | Matches | Matches | Matches | Publisher record and PDF opened; DOI redirect failed | Verified identity; resolver limitation |
| P7 | Confirmed in PDF | Confirmed in PDF | 2022 in PDF | CLEF in PDF | CEUR stable PDF; DOI not found in checked source | Verified identity from primary source |
| P8 | Confirmed in PDF | Confirmed in PDF | 2021 in PDF | CLEF in PDF | CEUR stable PDF; DOI not found in checked source | Verified identity from primary source |
| P9 | Confirmed in PDF | Confirmed in PDF | 2021 in PDF | CLEF in PDF | CEUR stable PDF; DOI not found in checked source | Verified identity from primary source |
| P10 | Matches record/PDF | Matches | 2026 | EACL Findings | Stable ACL record; DOI resolution untested | Verified identity; abstract discrepancy recorded |
| P11 | v2 matches record/PDF | Matches | v2 2024; v1 2023 | Preprint | Stable arXiv ID verified | v2 identity verified; v1 relation only partly checked |
| P12 | Matches record/PDF | Matches | 2025 | NAACL | Stable ACL record; DOI resolution untested | Verified identity |
| P13 | Confirmed in PDF | Confirmed in PDF | 2024 in PDF | CLEF in PDF | CEUR stable PDF; DOI not found in checked source | Verified identity from primary source |

## Citation tracing and deduplication

| Step | Seed → candidate | Evidence / outcome |
| --- | --- | --- |
| Backward | P3 → P11 | P3 reference list p. 255 names Hyben et al. (2023), under the earlier title. Latest arXiv record and v2 PDF checked; v1 inaccessible. |
| Forward | P11 → P12 | P12 reference list p. 10304 explicitly cites arXiv:2311.06121. Relevant check-worthiness experiment confirmed in §5.5. |
| Forward attempt | P2 → later works | S11 returned directories and possible citing works. No additional P2 citation edge was verified; this is not a completed citing-paper census. |
| Duplicate retrieval | P2 and P3 | Appeared again in search results; retained original IDs rather than counted as new studies. |
| Duplicate retrieval | P10 | ACL record, author pages, repository and Zenodo descriptions concern the same candidate; counted once. |
| Possible overlapping reports | P10 / P11 | Keep separate candidate records; do not combine their evidence or count independent replication until overlap is assessed. |

## Other discovered candidates — not yet full-text screened

Pending means no inclusion decision. These are retained so that prioritized screening does not silently discard less convenient findings.

| Candidate / locator | Why retained | Status |
| --- | --- | --- |
| https://aclanthology.org/2023.findings-emnlp.439/ — From Chaos to Clarity: Claim Normalization to Empower Fact-Checking | Potential LRQ3; semantic rewriting may differ from surface normalization | Pending |
| https://aclanthology.org/2021.sigdial-1.40.pdf — What to Fact-Check: Guiding Check-Worthy Information Detection in News Articles through Argumentative Discourse Structure | Context and evaluation | Pending |
| https://aclanthology.org/2022.coling-1.259.pdf — Harnessing Abstractive Summarization for Fact-Checked Claim Detection | May concern retrieval rather than worthiness; check I1/E1 | Pending |
| https://aclanthology.org/2020.icon-main.39/ — Claim extraction from text using transfer learning | Check task definition and relevance | Pending |
| https://doi.org/10.1145/3770077 — A Survey on Automatic Credibility Assessment Using Textual Credibility Signals in the Era of Large Language Models | Possible background and citation leads | Pending |
| https://ceur-ws.org/Vol-3740/paper-24.pdf — Overview of the CLEF-2024 CheckThat! Lab Task 1 on Check-Worthiness Estimation of Multigenre Content | Official dataset/task documentation | Pending |
| OpenFact CLEF 2024 report located through a university-repository search hit | Sampling / cross-lingual evidence; exact primary record still to resolve | Pending |
| Can LLMs automate fact-checking article writing? | Possible P2 citing work; primary record and relevant component not checked | Pending |

Author directories, venue indexes, generic learning-curve documentation and unrelated web pages were treated as navigation/non-study results, not included research evidence. Their presence does not establish a relevant publication.

## Counts for the assessed continuation set

- New candidates with targeted full-text screening: 8 (P6–P13).
- Include recommendations: 7 (P6–P10, P12–P13).
- Pending after full-text inspection: 1 (P11).
- Exclude decisions within this assessed set: 0.
- Independent human second screening completed: 0.
- Additional pending discovery records listed above: 8.
- Total search-engine hits and total duplicate hits: unavailable, not estimated.

These are assessed-set counts, not a complete review flow diagram. Existing pilot decisions remain separate. No target number of ten papers was imposed.

## Access and coverage limitations

- ACM DL homepage returned HTTP 403; IEEE Xplore homepage returned HTTP 418. Their native search interfaces were not searched successfully. Domain-restricted web discovery is not a substitute for full database coverage.
- No native Google Scholar search was performed; the protocol's first-100-results procedure remains outstanding.
- ACL coverage is limited to general web indexing, not its complete native result set.
- CEUR sources were reached through supplementary web discovery and direct PDF access.
- Protocol Q1 and Q5 were not rerun in this continuation; Q2–Q4 were executed with the ACL domain restriction only. Other source/query combinations remain outstanding.
- Supplementary queries, including the additional “check-worthy” spelling, are logged rather than silently substituted for Q1–Q5.
- Search results were prioritized for relevance to the identified gaps; returned records were not exhaustively screened. The pending queue records concrete study leads still needing review.
- Citation tracing verified selected links only. No full forward-citation index or saturation claim is made.
- Source PDFs were used for findings; full §9 extraction of these new papers and independent human screening remain pending.
- RQ2 has partial evidence from pruning, but a direct target-domain random-sample-size study was not established in this search. This is a limitation of this search, not proof of absence in the literature.

## Practical use in the research plan

Reviewer interpretation:

- RQ1: prioritize P6; use P10 and P12 to distinguish corpus, domain and language transfer.
- RQ2: use P13 to motivate controlling sample selection and class balance when varying size.
- RQ3: contrast P7 URL masking with P9 domain-preserving URL processing; P8 motivates testing transformations separately rather than attributing a pipeline effect to one step.

The next required work is §9 extraction for included new papers, human screening, and completion or explicit limitation of remaining search/snowballing coverage. Floor 4 remains In Progress.
