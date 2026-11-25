# Floor 4 — Testing Log

Updated: 2026-11-25.
Skill: review-manager.
Project: Claim Detection — Check-Worthiness.

This log records observed work and user-reported human checks. Historical run versions were not recorded; no version identifiers or unobserved reruns are invented.

## 1. Assignment requirements

Meeting 4 slides 53, 56 and 58 specify an instructor-provided list of ten sources, including two fabricated sources. Slide 56 requires the agent to identify both, avoid falsely flagging real sources, and state which details could not be found.

Slide 59 requires a protocol, source-verification tables, the acceptance test, an updated testing log, and a table checking the three slide-50 claims. The three-reference example on slide 48 is not the acceptance test.

## 2. Protocol-reading check

**Request:** Read the bundled protocol; summarize review questions, search sources and inclusion/exclusion criteria; report missing context without searching.

**Observed response:** The agent summarized LRQ1–LRQ4 and the review procedure. It raised missing research-question context, ambiguity about the constitution, verification-table differences and missing protocol version information.

**Clarifications supplied:** Use the constitution in Project Instructions; agent-requirements.md is a separate requirements document. Read rq-and-hypotheses.md without changing RQ1–RQ3. Merge bibliographic fields with individual verification statuses and supporting locations. Treat synthesis as an evidence comparison. Preserve search strings for the pilot.

**Assessment:** The requested protocol summary was produced. This is a functional check, not an official acceptance-test pass. No unrecorded skill-file edit or rerun is claimed.

## 3. Five-paper pilot

**Date:** 2026-11-25.
**Request:** Use Q1 for an ACL Anthology pilot; inspect up to five candidates; record query, access method and limits; stop after the pilot.

**Reported query:**

```text
site:aclanthology.org ("check-worthiness" OR "check worthiness" OR "checkworthy" OR "claim worthiness") AND (detection OR classification OR ranking)
```

**Access:** General web search restricted to ACL Anthology, not native database search.

**Observed first response:** Five candidates were listed from search records/excerpts; full-text decisions were unresolved. The response disclosed limits, but bibliographic “Matches” overstated the checks actually performed.

**Follow-up:** Open the same canonical records and PDFs, verify details, apply the criteria and provide supporting locations.

**Observed follow-up:** The agent reported inspecting the five records and PDFs. DOI resolution was not tested. The user supplied screenshots for title/author comparison.

**Evidence:** pilot-q1-acl-anthology.docx; pilot-q1-acl-anthology(1).docx.

**Assessment:** Limited pilot completed; neither a complete systematic search nor an acceptance test.

## 4. Slide-48 practice check

**Input supplied to the agent:**

1. Kitchenham & Charters (2007). Guidelines for performing systematic literature reviews in software engineering.
2. Wohlin (2012). Guidelines for snowballing in systematic literature studies and a replication in software engineering.
3. Doe & Roe (2023). No title, venue or DOI.

**Instruction:** Verify references; do not silently correct the input; distinguish citation errors from unidentified sources; return evidence, status and required action.

| Reference | Observed response | Assessment |
|---|---|---|
| Kitchenham & Charters (2007) | Identified a report copy and bibliographic record; disclosed incomplete primary-source confirmation and report-number differences. | Partial verification; did not invent unresolved fields. |
| Wohlin (2012) | Found 2014 and DOI 10.1145/2601248.2601268; disclosed that the ACM page was not opened. | Detected the incorrect year. |
| Doe & Roe (2023) | Found no identifiable match and requested a title, venue, DOI or link. | Correctly avoided treating a single unsuccessful search as proof of fabrication. |

Slide 48 explicitly labels its third example as fabricated. That answer-key information was not included in the practice prompt.

**Outcome:** Practice behavior documented; no formal Pass/Fail assigned. No subsequent Claude rerun is recorded.

## 5. Review extension and human decisions

Further AI-assisted searches, citation tracing and extraction are documented in search-extension.md and literature-extraction.md. They are subsequent work, not additional Claude runs.

The group retained P5 because it explicitly evaluates check-worthiness and excluded P4 from the main extraction under its strict task criterion.

For P11, the AI recommended supplementary handling because potential overlap with P10 was unresolved. The group chose inclusion. Both publications are retained; overlapping data or experiments must not be treated as independent evidence.

Evgeny Sudman reported reviewing the literature extraction. Details marked “Not verified” remain unresolved. This statement does not certify unestablished details or claim a blinded independent screening procedure.

The review contains 13 records: 12 included publications and one excluded. The relationship between P10 and P11 remains unverified.

## 6. Slide-50 claim verification

Results are recorded in floor-4-slide-claims.md.

- Claim 1: supported for the replication described by Wohlin.
- Claim 2: the inspected accepted manuscript gives seven questions, not four; one or more positive answers suggest grey-literature inclusion.
- Claim 3: the inspected author manuscript supports the timing comparison.

The presentation requests the published journal/book versions for claims 2 and 3. Those exact full-text versions were not accessible in this check; the companion table records that limitation.

## 7. Official acceptance test

**Status: NOT RUN.**
**Reason:** The instructor's ten-source list has not been supplied in the available conversation or materials. The presentation describes the test but does not provide its ten references.

The five-paper pilot, the slide-48 practice and the review's included publications do not replace this list.

When available, record:
- execution date and actual skill/protocol version;
- exact request and response;
- whether both fabricated entries were identified;
- whether any real source was falsely flagged;
- missing fields, corrections and any actual rerun;
- Pass or Fail under slide 56.

## 8. Current status

Floor 4 — In Progress.

The protocol, pilot, practice log, review extension and claim-check table are documented. Official acceptance-test success is not claimed. Published-version checks for claims 2–3 and unresolved literature fields remain explicitly limited.

AI assistance was used to draft and revise these materials. Slides 49 and 58 require the group's own protocol decisions; this log does not claim that the AI-assisted draft was originally written without AI.

