# Preliminary Pilot: Q1 Search in ACL Anthology

Search log and verification/screening table, updated after record-page and full-text checks of P1–P5. Update date: 2026-11-25.

| PRELIMINARY PILOT — NOT A COMPLETED SYSTEMATIC SEARCH<br>One query (Q1, the general check-worthiness search string), one source (ACL Anthology, accessed via general web search restricted with site:aclanthology.org), five candidate records. This update opens each canonical record page and full-text PDF. Second screening by a human group member: PENDING. Instructor's ten-source acceptance test: NOT RUN; no pass is claimed. This is not a literature review; no extraction or synthesis has been done. |
| --- |

## 1. Task and scope

- Task: verify the five candidate records from the pilot (P1–P5) against canonical ACL Anthology record pages and full-text PDFs, and screen them against protocol.md §5–§6. No further papers were searched for.

- Scope label (corrected): Q1 is the general check-worthiness search string. It is not tied to LRQ1. Each candidate is assessed for relevance to any of LRQ1–LRQ4. The earlier version of this document labelled the pilot as an LRQ1 pilot; that label was wrong.

- Bibliographic verification and screening are kept separate: a verified record can still be excluded or remain Pending on relevance.

- Protocol version: Not stated in protocol.md. Group approval of the protocol: not confirmed.

- Constitution: I checked the instruction text available in this conversation. It contains a block of operating rules (role, no hallucinated sources, justification and assumptions, [UNVERIFIED] tag, PII protection, step-by-step confirmation, critic not author, English and concision). It carries no title or path identifying it as constitution/agent-constitution.md, and no such file exists in the accessible project files. I applied the rule block as operating rules but cannot confirm it is the constitution. The group should confirm, or supply the file.

- RQ1–RQ3 in rq-and-hypotheses.md were not modified.

- Second screening by a human group member (protocol §7 step 8): Pending; not simulated. All decisions below are agent suggestions applying the written criteria; final decisions rest with the group.

- Instructor's ten-source list and acceptance test: not provided, not run. No pass is claimed.

- Assumptions: (a) the ACL Anthology record and PDF are treated as authoritative for bibliographic fields (the Anthology states that it treats PDFs as authoritative); (b) the fetch tool returns extracted text, so page numbers are inferred from running page footers and table values were read from extracted text, not from page images; (c) "Verified" means title, authors, year, venue and DOI/stable record agree across the canonical record and the PDF title page.

## 2. Search log

### 2.1 Original search log (unchanged)

| Date | Source | Exact query | Filters and limits | Results | Access limitations |
| --- | --- | --- | --- | --- | --- |
| 2026-11-25 | ACL Anthology via general web search restricted with site: operator (run 1, standard mode). Not a native database search. | site:aclanthology.org ("check-worthiness" OR "check worthiness" OR "checkworthy" OR "claim worthiness") AND (detection OR classification OR ranking) | Q1 unchanged apart from the site: operator. No year filter. Title/abstract/keyword scope not controllable. At most five candidates inspected. | Total hit count: Not available. The tool returned 9 documents, including mirror hosts (preview.aclanthology.org) and arXiv items despite the restriction. | Boolean handling by the engine unknown. Ranking is not ACL Anthology's own. Coverage incomplete. |
| 2026-11-25 | Same as above (run 2, extended mode) | Identical query | Same as above | Total hit count: Not available. The tool returned 10 documents, again including some arXiv items. | Same as above. |

Only records on canonical aclanthology.org were treated as ACL Anthology hits. arXiv and mirror-host items were not screened. Two further ACL Anthology hits (2025.ranlp-1.49; 2025.banglalp-1.10) appeared in run 2 but were not inspected because of the five-paper cap; they remain Pending and unscreened.

### 2.2 Follow-up: locator searches (existing candidates only)

| Date | Locator query (standard mode) | Purpose | Notes |
| --- | --- | --- | --- |
| 2026-11-25 | aclanthology.org 2020.findings-emnlp.43 Claim Check-Worthiness Detection as Positive Unlabelled Learning | Locate the canonical record for P2 (the fetch tool refused a URL it had not seen in results). | Locator search for an existing candidate. No new candidate added. Result count: Not available. |
| 2026-11-25 | aclanthology.org/2024.acl-long.104 | Identify the title and canonical record of P4 (title was not retrieved in the original pilot). | Locator search. Unrelated hits for other volumes (2024.eacl-long.104, 2023.acl-long.104) were ignored. Result count: Not available. |
| 2026-11-25 | aclanthology.org/2024.findings-emnlp.830 Factcheck-Bench | Identify and locate the canonical record of P5. | Locator search. No new candidate added. Result count: Not available. |

### 2.3 Follow-up: pages opened

| ID | URL opened (web_fetch) | Outcome | Notes |
| --- | --- | --- | --- |
| P1 | https://aclanthology.org/N18-5006/ | Opened | Record page: title, authors, venue, year, pages, DOI, bibkey read. |
| P1 | https://aclanthology.org/N18-5006.pdf | Opened | Full text (pp. 26–30) returned. |
| P2 | https://aclanthology.org/2020.findings-emnlp.43 | Refused, then opened | First attempt refused (URL not in prior results). Opened after the locator search; resolves to the canonical URL with trailing slash. |
| P2 | https://aclanthology.org/2020.findings-emnlp.43.pdf | Opened | Full text (pp. 476–488) returned. |
| P3 | https://aclanthology.org/2024.fever-1.27/ | Opened | Record page read. |
| P3 | https://aclanthology.org/2024.fever-1.27.pdf | Opened | Full text (pp. 245–263) returned. |
| P4 | https://aclanthology.org/2024.acl-long.104 | Opened | Record page read (canonical URL with trailing slash). |
| P4 | https://aclanthology.org/2024.acl-long.104.pdf | Opened | Full text (pp. 1890–1912) returned, including appendices. |
| P5 | https://aclanthology.org/2024.findings-emnlp.830/ | Opened | Record page read. |
| P5 | https://aclanthology.org/2024.findings-emnlp.830.pdf | Opened | Full text (pp. 14199–14230) returned. |
| P1–P5 | https://doi.org/ links shown on record pages | Not tested | The fetch tool refused doi.org URLs not previously returned in results (tested for P1 and P3; the same restriction is assumed for the rest, untested). DOI resolution remains Pending for the group. |

## 3. Verification and screening table

"Matches" means the canonical record and the fetched PDF agree. Supporting locations are pages and sections of the PDF, inferred from running footers. Evidence categories (protocol §5) are given where a decision is Include or if the paper were included. No extraction or synthesis has been performed.

| ID | Reference (as shown on record) and links | Title check | Authors check | Year check | Venue check | DOI or record check | Supporting location | Verification status | Decision | Criterion and reason |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| P1 | Jaradat, Gencheva, Barrón-Cedeño, Màrquez & Nakov (2018). ClaimRank: Detecting Check-Worthy Claims in Arabic and English. In Proc. NAACL-HLT 2018: Demonstrations, pp. 26–30, New Orleans, Louisiana. ACL.<br>Record: [aclanthology.org/N18-5006/](https://aclanthology.org/N18-5006/)<br>PDF: [aclanthology.org/N18-5006.pdf](https://aclanthology.org/N18-5006.pdf) | Matches (record; PDF p. 26) | Matches: 5 authors, same order (record; PDF p. 26) | Matches: 2018, June (record; PDF p. 26) | Matches: NAACL, Demonstrations volume (record; PDF p. 26) | Matches: DOI 10.18653/v1/N18-5006 listed on record; canonical record URL confirmed. doi.org resolution not tested. | p. 26: §1–2 (task, related work)<br>p. 27: §3.1–3.3 (model)<br>pp. 28–29: §3.5 and Table 1 (evaluation)<br>p. 29: §5 | Verified (stable record confirmed; DOI resolution not tested) | Include (agent-suggested; second screening Pending) | I1 met: system for detecting and ranking check-worthy claims (p. 26; §3.3 p. 27).<br>I2: LRQ4 (training data from fact-checkers' annotations of debates, §2 p. 26; MAP, R-Pr, P@k, Table 1 p. 29). LRQ1 only weakly: cross-language (English debates to Arabic translations, §3.5 p. 28); no non-debate evaluation is reported although §5 p. 29 says the system can handle other text.<br>I3 met: method and results (Table 1). I4–I6 met.<br>Not excluded for being a demonstration paper; actual content meets I1–I6.<br>Category: primary empirical study, limited. Concerns: one train/test split of debates (§3.5); runs and uncertainty Not reported; F1 Not reported (MAP etc.); authors note results are not comparable with their earlier setup (footnote 2, p. 28). |
| P2 | Wright & Augenstein (2020). Claim Check-Worthiness Detection as Positive Unlabelled Learning. In Findings of ACL: EMNLP 2020, pp. 476–488, Online. ACL.<br>Record: [aclanthology.org/2020.findings-emnlp.43/](https://aclanthology.org/2020.findings-emnlp.43/)<br>PDF: [aclanthology.org/2020.findings-emnlp.43.pdf](https://aclanthology.org/2020.findings-emnlp.43.pdf)<br>Supplementary versions (not main record): see Section 4. | Matches (record; PDF p. 476) | Matches: 2 authors (record; PDF p. 476) | Matches: 2020, November (record; PDF p. 476) | Matches: Findings of EMNLP 2020 (record; PDF p. 476) | Matches: DOI 10.18653/v1/2020.findings-emnlp.43 listed; canonical record confirmed. doi.org resolution not tested. | pp. 477–478: §2.1 (task definition)<br>p. 480: §3.4 (BERT, fine-tuning)<br>pp. 480–482: §4.1 (datasets)<br>pp. 481–483: Tables 1–3<br>p. 483: Table 4<br>p. 486: App. B.5 (metrics) | Verified (stable record confirmed; DOI resolution not tested) | Include (agent-suggested; second screening Pending) | I1 met. I2: LRQ1 and LRQ2 partially: a Wikipedia-trained model is transferred to Twitter (PHEME) and political speeches by fine-tuning on target data (§3, p. 478; §3.4, p. 480), so this is not zero-shot; target fine-tuning sample sizes varied: Not reported. LRQ4: datasets and annotation sources (§4.1; §4.5 and Table 4, p. 483).<br>I3 met (primary empirical study). I4–I6 met.<br>Concerns: PHEME is rumour detection (rumour/non-rumour), used as a Twitter proxy (§4.1, p. 481); mean ± SD over 15 seeds (§4, p. 480); no significance test seen; F1 variant: micro-F1 in Table 2, averaging for Table 1 not stated beyond App. B.5; MAP for political speeches (Table 3). Results across datasets must not be ranked against each other. |
| P3 | Majer & Šnajder (2024). Claim Check-Worthiness Detection: How Well do LLMs Grasp Annotation Guidelines? In Proc. Seventh FEVER Workshop, pp. 245–263, Miami, Florida, USA. ACL.<br>Record: [aclanthology.org/2024.fever-1.27/](https://aclanthology.org/2024.fever-1.27/)<br>PDF: [aclanthology.org/2024.fever-1.27.pdf](https://aclanthology.org/2024.fever-1.27.pdf)<br>Supplementary versions (not main record): see Section 4. | Matches (record; PDF p. 245) | Matches: Laura Majer, Jan Šnajder (record; PDF p. 245) | Matches: 2024, November (record; PDF header p. 245) | Matches: Seventh FEVER Workshop (record; PDF p. 245) | Matches: DOI 10.18653/v1/2024.fever-1.27 listed; canonical record confirmed. doi.org resolution not tested. | pp. 247–248: §3 and Table 2 (datasets, label distribution, agreement)<br>pp. 248–249: §4<br>p. 250: Table 3 (binary F1), §5.1<br>p. 251: leakage remark<br>p. 253: Limitations<br>p. 257: App. B (single run) | Verified (stable record confirmed; DOI resolution not tested) | Include (agent-suggested; second screening Pending) | I1 met (claim detection and check-worthiness detection, p. 245). I2: LRQ4 (five datasets across genres incl. CLEF 2022 tweets; guidelines; class distribution and agreement, Table 2 p. 248). LRQ1 only partially: LLM prompting compared across domains; no trained-model source-to-target transfer; BERT baselines are trained per dataset (p. 250). LRQ2: few-shot prompting, not target fine-tuning size; training sample sizes Not reported.<br>I3 met. I4–I6 met.<br>Category: primary empirical study. Concerns: evaluated instances are subsets (Table 2); NEWS baselines use a different test set (p. 250); one run per model and prompt (App. B, p. 257); possible data leakage on ClaimBuster (pp. 251, 253). Metric: binary F1 (Table 3 caption). |
| P4 | Ni, Shi, Stammbach, Sachan, Ash & Leippold (2024). AFaCTA: Assisting the Annotation of Factual Claim Detection with Reliable LLM Annotators. In Proc. 62nd ACL (Vol. 1: Long Papers), pp. 1890–1912, Bangkok, Thailand. ACL.<br>Record: [aclanthology.org/2024.acl-long.104/](https://aclanthology.org/2024.acl-long.104/)<br>PDF: [aclanthology.org/2024.acl-long.104.pdf](https://aclanthology.org/2024.acl-long.104.pdf)<br>Other versions: none encountered; not searched for. | Matches (record; PDF p. 1890) | Matches: 6 authors, same order (record; PDF p. 1890) | Matches: 2024, August (record; PDF header p. 1890) | Matches: ACL 2024 main conference, Volume 1 (record; PDF p. 1890) | Matches: DOI 10.18653/v1/2024.acl-long.104 listed; canonical record confirmed. doi.org resolution not tested. | p. 1891: Table 1<br>pp. 1892–1893: §2.1–2.2<br>p. 1893: choice of verifiability over check-worthiness<br>pp. 1894–1895: §4, Table 2 (p. 1894)<br>pp. 1896–1897: §5.5, Figs. 3–4<br>p. 1898: §7.1<br>p. 1902: App. B<br>p. 1907: App. L | Verified (stable record confirmed; DOI resolution not tested) | Pending (uncertain case for group) | I1 borderline: the paper concerns factual-claim (verifiability) detection for fact-checking and states that it does not target check-worthiness (§2.2 p. 1893; §7.1 p. 1898), yet it analyses check-worthiness definitions (§2.1 p. 1892; Table 1 p. 1891) and re-annotates CheckThat!-2021 tweets (p. 1894).<br>E1 not clearly triggered (not truth verification only), but the check-worthiness component is conceptual rather than a detection result.<br>I2: LRQ4 (definitions; guideline, App. B p. 1902; Cohen's κ 0.69 and 0.58, p. 1894; temporal train/test split, p. 1894). LRQ2 only by analogy (accuracy versus training size, 3 seeds, Figs. 3–4; significance tests, App. L p. 1907). Metrics: accuracy and κ, not positive-class F1.<br>I3–I6 met. Group decision needed on whether verifiability-based claim detection satisfies I1. |
| P5 | Wang, Gangi Reddy, Mujahid, Arora, Rubashevskii, Geng, Mohammed Afzal, Pan, Borenstein, Pillai, Augenstein, Gurevych & Nakov (2024). Factcheck-Bench: Fine-Grained Evaluation Benchmark for Automatic Fact-checkers. In Findings of ACL: EMNLP 2024, pp. 14199–14230, Miami, Florida, USA. ACL.<br>Record: [aclanthology.org/2024.findings-emnlp.830/](https://aclanthology.org/2024.findings-emnlp.830/)<br>PDF: [aclanthology.org/2024.findings-emnlp.830.pdf](https://aclanthology.org/2024.findings-emnlp.830.pdf)<br>Supplementary versions (not main record): see Section 4. | Matches (record; PDF p. 14199) | Matches: 13 authors, same order (record; PDF p. 14199) | Matches: 2024, November (record; PDF header p. 14199) | Matches: Findings of EMNLP 2024 (record; fetched PDF header). Discrepancy: an earlier search-engine rendering of the same PDF URL showed the header as "EACL 2024". Group to check the PDF. | Matches: DOI 10.18653/v1/2024.findings-emnlp.830 listed; canonical record confirmed. doi.org resolution not tested. | p. 14200: §2, subtask (3)<br>pp. 14203–14204: §3.2 (annotation)<br>p. 14204: Table 1<br>p. 14206: §4.2, Table 3<br>p. 14208: Limitations<br>p. 14217: App. B.3<br>p. 14222: App. C.3 | Verified (stable record confirmed; DOI resolution not tested; venue-header discrepancy noted) | Pending (uncertain case for group) | I1 partial: check-worthiness identification is one of eight subtasks of a benchmark for fact-checking LLM output (§2 p. 14200; Table 3 p. 14206), and the text is ChatGPT output, not debates or social media.<br>E1 not strictly triggered (the paper has check-worthiness labels and results), but the component is secondary to verification and revision.<br>I2: LRQ4 only (guideline, App. C.3 p. 14222; label counts, Table 1 p. 14204). Not relevant to LRQ1–LRQ3.<br>Concerns: 94 instances (Limitations p. 14208); check-worthy claims are 661 of 678 (§4.2 p. 14206); metrics are accuracy and macro-F1, not positive-class F1; annotator agreement statistic Not reported (difficulty noted, App. B.3 p. 14217).<br>I3–I6 met. Group decision needed. |

## 4. Source links and versions

Per protocol §4, the final published version is the main record; preprints and related versions are linked as supplementary and were not used for bibliographic verification.

| ID | Main record (final published version) | Full-text PDF | Supplementary or related versions (not main record) |
| --- | --- | --- | --- |
| P1 | [https://aclanthology.org/N18-5006/](https://aclanthology.org/N18-5006/) | [https://aclanthology.org/N18-5006.pdf](https://aclanthology.org/N18-5006.pdf) | None encountered. |
| P2 | [https://aclanthology.org/2020.findings-emnlp.43/](https://aclanthology.org/2020.findings-emnlp.43/) | [https://aclanthology.org/2020.findings-emnlp.43.pdf](https://aclanthology.org/2020.findings-emnlp.43.pdf) | Preprint: [arXiv:2003.02736 (listed with v1 5 Mar 2020 and v2 16 Sep 2020; title and authors match; not compared in full)](https://arxiv.org/abs/2003.02736)<br>Related: [arXiv:2108.10274, thesis excerpt "Towards Explainable Fact Checking" reproducing this abstract; not compared in full. E2 candidate.](https://arxiv.org/pdf/2108.10274) |
| P3 | [https://aclanthology.org/2024.fever-1.27/](https://aclanthology.org/2024.fever-1.27/) | [https://aclanthology.org/2024.fever-1.27.pdf](https://aclanthology.org/2024.fever-1.27.pdf) | Preprint: [arXiv:2404.12174 v2](https://arxiv.org/html/2404.12174v2)<br>[arXiv:2404.12174 v1](https://arxiv.org/html/2404.12174v1)<br>Same title. The abstracts of v1, v2 and the published version differ in wording (seen in search results). Authorship of the arXiv versions was not checked. Use the published version. |
| P4 | [https://aclanthology.org/2024.acl-long.104/](https://aclanthology.org/2024.acl-long.104/) | [https://aclanthology.org/2024.acl-long.104.pdf](https://aclanthology.org/2024.acl-long.104.pdf) | None encountered; not searched for. |
| P5 | [https://aclanthology.org/2024.findings-emnlp.830/](https://aclanthology.org/2024.findings-emnlp.830/) | [https://aclanthology.org/2024.findings-emnlp.830.pdf](https://aclanthology.org/2024.findings-emnlp.830.pdf) | Preprint: [arXiv:2311.09000 v3](https://arxiv.org/pdf/2311.09000v3)<br>Same title. The abstract wording differs from the published abstract (seen in search results). Not compared in full. |

## 5. Terminology notes (search strings unchanged)

- Q1 variants may miss papers using the adjective form "check-worthy" (as in the P1 title).

- Candidate additional terms, suggested only and untested: "check-worthy claim detection", "claim detection", "factual claim detection", "claim prioritization", "verifiable claim". P4 shows that some papers separate verifiability from check-worthiness, which affects term choice.

- Whether the engine matched the spelling "checkworthiness" is unknown.

## 6. Human checks required

- Second screening of P1–P5 by a group member; P1–P3 are suggested Include, P4 and P5 are uncertain cases.

- Decide I1 for P4 (verifiability-based claim detection) and for P5 (check-worthiness as a subtask of LLM-output fact-checking).

- Test DOI resolution through doi.org for P1–P5 (the fetch tool refused doi.org URLs).

- Check the P5 PDF header (EMNLP 2024 in the fetched PDF; "EACL 2024" in an earlier search-engine rendering).

- Open the PDFs and confirm table values and page numbers on the page images before any extraction.

- Decide how the arXiv versions (P2, P3, P5) and the thesis excerpt (P2) are handled under E2, and check authorship and wording differences of the P3 arXiv versions.

- Confirm whether the Project Instructions rule block is the constitution, or supply constitution/agent-constitution.md.

- Confirm the protocol version and group approval. Provide the instructor's ten-source list when ready.

- Snowballing and extraction were not performed. Sources cited in rq-and-hypotheses.md (Nenno 2024, Meng et al. 2024, Hasanain et al. 2024) were not found or verified in this pilot: [UNVERIFIED].

Stopped after updating the five records; awaiting group confirmation before any further step.
