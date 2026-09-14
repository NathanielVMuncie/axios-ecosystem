# Methodology smoke test WCAG22-01
Date: 2026-09-14
Outcome: Functional checks passed; methodology promotion NOT approved.
Scope: A narrow live-source lookup and isolated verification, not a complete deep-research validation.

## Decision and authority
The existing repository candidate v0.9 remains controlling. Its Section 16 requires representative tasks, a simpler baseline, matched conditions, and a promotion record. The conversational v1.1 draft did not inspect that existing gate and must not silently replace it. Its single-question pilot is classified as a smoke test only. Phase 1 remains In Progress.
Source: ../candidates/deep-research-methodology-candidate-v0.9.md, Section 16.
Candidate blob inspected: 2b9de6744ab9859582833f1fb05ab49c3453311d.

## Inquiry and frozen criteria
Question: Under WCAG 2.2, compare AA and AAA text contrast requirements, large-text definition, logo exceptions, and whether 4.49:1 meets a required 4.5:1.
Excluded: whole-site conformance, law, empirical readability and Axios architecture.
Reference key was recorded before researcher output and withheld from researcher/verifier. Setup source discovery preceded key creation; this is not a fully preregistered study.
Acceptance: five correct source-supported answers; all consequential claims checked; false rounding claim rejected; no whole-site inference; no added paid resource.
Budget: 60-minute ceiling, 12 search/open actions. In-document finds tracked separately. Token telemetry unavailable.
A timestamp was recorded during execution at 13:31:10Z; the initial start was not instrumented, so precise end-to-end elapsed time is unavailable. This prevents claiming complete timing compliance.

## Reference key and results
C1: AA ordinary text >=4.5:1; large >=3:1, subject to exceptions. Researcher and verifier: pass.
C2: AAA ordinary text >=7:1; large >=4.5:1, subject to exceptions. Both: pass.
C3: Large text >=18pt regular or >=14pt bold, or equivalent CJK size; delivered size before user resizing. Both: pass.
C4: Logo/brand-name text exempt under these criteria; not all branded copy. Both: pass.
C5: 4.49:1 does not meet a required 4.5:1; rounding is not allowed. Both: pass.

Sources and exact locators:
- https://www.w3.org/TR/WCAG22/#contrast-minimum — SC 1.4.3.
- https://www.w3.org/TR/WCAG22/#contrast-enhanced — SC 1.4.6.
- https://www.w3.org/TR/WCAG22/#dfn-large-scale — definition and sizing notes.
- https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html#intent — rounding and corporate identity guidance.
Access date: 2026-09-14. Retrieved Recommendation dated 2024-12-12; Understanding revision date not established.

## Evidence appraisal
Directness and applicability: direct requirements for the named standard; informative guidance explains rounding and branding boundaries.
Authority: W3C is the originating standards organization.
Methodological quality: normative specification supports what the standard requires, not causal effectiveness.
Independence: one institutional origin, not multiple independent replications.
Recency: version-specific lookup; live retrieval; no comprehensive errata audit.
Incentives: accessibility and standards adoption; no independent empirical validation inferred.
Confidence: high for these narrowly scoped interpretations.

## Isolation and challenge
Researcher and verifier were separate agents started without conversation history. Researcher received the neutral question and starting source URLs, not the key. Verifier received exact claims and URLs but no researcher rationale or reference key; it was claim-aware, not answer-blind.
They shared model family/provider and source origin. This establishes context separation, not independent model or empirical evidence.
Challenge X1, separate from the actual answer: “4.49:1 qualifies for 4.5:1 because rounding to one decimal is permitted.”
Verifier rejected X1 using explicit no-rounding guidance, including its 4.499 example.
Verifier checked incidental and logo exceptions; no material counterexample to the qualified claims was found.
No correction was required to C1–C5. Repair regression remains untested.

## Activity log
Coordinator setup: two searches (W3C AA contrast; W3C AAA contrast), then two page opens.
Researcher: four opens, zero searches, two in-document finds. Three unique pages retrieved; only two used substantively. Third was Understanding Contrast Enhanced, not relied upon.
Verifier: two opens, zero searches, five finds for thresholds, size, rounding and logo exceptions.
Total: 10 search/open actions, plus 7 finds. Counting every web operation yields 17; these metrics must not be conflated.
No new subscription, paid API or infrastructure was purchased. Exact token use and cost telemetry unavailable.
This report summarizes visible tool records; it is not a full raw trace export.

## Scorecard
Five required claims supported and checked: PASS (5/5).
Seeded false claim rejected: PASS (1/1).
False corrections to correct claims: zero observed.
Source independence limitations disclosed: PASS.
No whole-site conformance inflation: PASS.
Search/open envelope: PASS (10/12); action-definition ambiguity disclosed.
Precisely measured elapsed time: NOT ESTABLISHED.
Baseline advantage: NOT TESTED.
Unfamiliar landscape, conflicting commercial evidence, benchmark transfer, changing-current-state cases: NOT TESTED.
Repair/regression: NOT TESTED.
Complete Section 16 promotion gate: NOT PASSED.

## Required next gate
Before further execution, freeze the repository-aligned multi-category pilot, simpler baseline, matched observable budgets, evaluator criteria, and timing instrumentation. Do not weaken this gate after observing smoke-test results.
This is a material difference from the one-question plan previously supplied in chat. No claim of full methodology completion, universal superiority, or validated cost is warranted.
