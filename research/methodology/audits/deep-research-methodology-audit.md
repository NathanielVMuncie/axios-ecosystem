# Independent Audit of Deep Research Method Selection

## 1. Audit verdict

**Revise substantially. Retain the proposal as a source of candidate practices; do not adopt it as an established operational protocol.**

The central combination—iterative synthesis, bounded parallel work, and explicit verification—is a defensible starting hypothesis for some research tasks. The supplied PDF does not establish that its particular combination, phase order, or resource limits is generally superior. No identified experiment evaluates its complete P0–P5 protocol.

The principal reasons are:

1. **Evidence is transferred between unlike interventions.** The tested TTD-DR system includes multiple agents, planning, parallel candidate generation, and component optimization. Its results cannot simply be assigned to a stripped-down, single-context draft loop. DeepVerifier likewise evaluates a richer verification intervention than one fresh-context review.[^1][^2][^3]
2. **Several consequential claims require correction.** These include the HLE-Search result, verifier improvement units and subsets, the denominator of the 15× token claim, the supposed abandonment of multi-agent research by LangChain, and the claim that only one cited work has conference publication status.[^3][^5][^6][^8][^12]
3. **The architecture argument overreaches.** Controlled comparisons exist, including counterevidence already available before the stated compilation date. They support task-dependent choices, with imperfect controls and substantial limits on transfer.[^4][^8][^9]
4. **The operational gates are internally inconsistent.** Required change on every retrieval round conflicts with termination after unchanged rounds. Verification runs only once, although its defects may require new research and subsequent rechecking. Downgrading confidence does not necessarily resolve a critical defect.
5. **The cost and independence claims are insufficiently specified.** No measured basis is supplied for the proposed protocol’s 2–4× cost. Neither multiple subscriptions nor a change of vendor establishes additional evidence independence or zero marginal expenditure.

**Candidate status:** the revised protocol below is suitable for review and a bounded pilot. Critical adoption blockers remain: no end-to-end validation of this candidate, no calibrated verifier performance for an eventual task class, and no verified execution-resource envelope. These do not prevent delivery of an audited candidate; they prevent calling it finalized, approved, or generally validated.

## 2. Input, chronology, and evidence standard

The complete six-page **deep-research-method-selection.pdf** was readable, including the architecture comparison on pages 2–3, the phase gates on pages 3–4, the failure-control table on page 5, and the bibliography on pages 5–6. No page or visible text block was missing. The bibliography lacks complete author, version, and access-date records; its BenchLM reference lacks a direct link.

The document states **30 August 2026** as its compilation date. That statement is not independently authenticated. The attached PDF’s creation metadata records **12 September 2026**; this is compatible with a later export and does not establish when the underlying research was performed. The audit uses 30 August as the proposal’s asserted evidence cutoff, not as proven provenance. Source access dates for this audit are **12 September 2026**.

The major corrections below rely on evidence available before that cutoff. In particular, the single-agent paper’s April revision, the debate paper’s July revision, the July ACL proceedings, and the 2025 NeurIPS proceedings predate it. A subsequently published September 1 demonstrator, LLMpedia, is considered only as a limited supplement about claim-level verification and insufficient evidence; it is not evidence that the PDF should have known earlier.[^21]

Current repository pages and leaderboards are mutable. Steel’s accessed page says it was updated September 4; it cannot authenticate what two aggregators showed during the original session.[^18] The dated July 2025 LangChain author account is sufficient to adjudicate the narrower historical claim about its design change.[^12]

**Assessment labels:** supported means the available evidence supports the precisely bounded claim; partially supported means only a narrower claim or component is justified; unsupported means the stated conclusion lacks adequate evidence; contradicted means the source or protocol supplies contrary evidence; unverifiable means a material access or provenance gap prevents adjudication. None of these labels substitutes for a description of the study’s limitations.

Reported experimental results were checked against accessible primary text, tables, methods, and publication records. They were not independently rerun. No validity is inferred solely from peer review, institutional affiliation, repeated citations, or source count. Analytical objections and proposed controls below are distinguished from measured results.

## 3. Claim audit table

Locations refer to printed PDF page numbers and section/phase labels. “R” references point to the study-condition records in Section 4; numbered references link to original sources.

| ID / consequential claim | PDF location | Original citation | Verification result | Evidence | Necessary correction |
|---|---|---|---|---|---|
| C01. Sequential depth, retrieval-only parallel breadth, and isolated critique are the evidence-backed default. | p.1 §01; p.6 boundary | Combined literature | **Partially supported** | Different studies support different components; none tests this complete combination. | Present it as a conditional candidate; select the method using task structure and a resource envelope. |
| C02. No public study isolates architecture from model and budget; uncontrolled gains measure spend, not design. | p.2 caution; p.5 §07 | Anthropic; general assertion | **Contradicted** as a blanket claim | R1, R4, and R5 contain controlled comparisons, although controls remain incomplete. | State which confound remains in each comparison. An uncontrolled result mixes effects; it does not prove that architecture contributes zero. |
| C03. Single agents match/beat every tested variant at every budget above 100 tokens; degrade only with context quality. | p.2 single-agent row; p.3 P2 | 2604.02460 | **Contradicted** in its universal form | R1 documents score exceptions and narrow accounting. | Retain a tendency on the tested tasks. Remove “every,” the unbounded budget extrapolation, and the exclusive explanation of failure. |
| C04. Token expenditure explains about 80% of browsing performance variance; a model upgrade beats doubled tokens. | p.2 caution | Anthropic Engineering | **Partially supported** | The lab reports this analysis and a specific Sonnet-version comparison.[^5] | Attribute it to that internal analysis. Explained variance is not a causal decomposition or a universal exchange rate. |
| C05. Multi-agent research gains 90.2%; about 15× is its cost relative to the single-agent backbone. | p.2 flat-MAS row; p.4 §05 | Anthropic Engineering | **Partially supported** | R2 confirms the report and corrects the denominator. | Separate quality and token comparisons; do not use 15× as a controlled MAS-versus-SAS research ratio. |
| C06. LangChain abandoned the supervisor/multi-agent pattern for a simpler loop. | p.2 flat-MAS row; p.6 sources | open_deep_research | **Contradicted** | Its dated author account retains multi-agent context gathering and moves writing to the end.[^12] | Describe the removal of parallel section writing, not the removal of multi-agent retrieval. |
| C07. MAST supplies 1,600+ traces, seven frameworks, 14 modes, three categories, κ=0.88. | p.2 hierarchy row | 2503.13657 | **Supported**, with qualification | R6 confirms the numbers and distinguishes expert agreement from automated annotation. | Do not imply every trace received the same human annotation procedure. |
| C08. MAST establishes that increasing hierarchy depth multiplies misalignment and warrants rejecting hierarchy. | p.2 hierarchy row | MAST | **Unsupported** | It is not a randomized depth-only ablation. | Treat hierarchy risk as a design concern; assess decomposition and coordination costs empirically. |
| C09. TTD-DR wins 74.5% on DeepConsult, gains 7.7% on HLE-Search and 1.7% on GAIA. | p.2 iterative row | 2507.16075; Google Research | **Partially supported; HLE attribution contradicted** | R3 preserves the correct table values. | HLE-Search: **+4.8 percentage points**; HLE-Full: **+7.7 points**; GAIA: **+1.7 points**. A preference win rate is not factual accuracy. |
| C10. Draft-first inverts planning and is independently ablated as the mechanism of TTD-DR’s gains. | p.3 P1 | TTD-DR | **Unsupported** | R3 describes a compound intervention with a retained planning stage. | An optional preliminary draft is supported in that setting; neither eliminating planning nor mandatory unsupported drafting is established. |
| C11. OOLONG rises 0.44→0.79 at 128k; recursion guarantees coverage. | p.2 recursive row | RLM / LangChain | **Partially supported** | R7 confirms a small proof of concept with a mixed score. | Identify the harness experiment. A correct completed loop can prove visitation; it cannot prove accurate extraction, classification, or cross-chunk reasoning. |
| C12. Competitive/consensus debate can harm; only collaborative protocols beat self-consistency. | p.2 debate row | 2510.20963; 2605.00914 | **Partially supported** | R4 and R8 show protocol-sensitive outcomes and positive alternatives. | Retain the caution against unguided debate. Remove the universal “only”; specify task, model, metric, and budget. |
| C13. K=1→4 raises pass@K roughly 50%, while practical selection lags. | p.3 verifier row | 2602.18998 | **Supported** for the reported setting | R9 distinguishes relative oracle improvement from selected accuracy. | Label it an average relative improvement in an upper-bound metric, not a 50-point deployed gain. |
| C14. Rubrics improve verifier meta-F1 by 12–48%. | p.3 verifier row | DeepVerifier | **Partially supported** | R10 gives the actual ablation values. | Use **11.63–48.17 F1 points** for those table differences; the compared baselines are specific ablations. |
| C15. Verification adds 8–11% end-to-end accuracy on hard GAIA/XBench. | p.3 verifier row | DeepVerifier | **Partially supported** | R10 separates dataset, model, peak, and final results. | Correct the XBench range and distinguish percentage points, best-round performance, and final-round performance. |
| C16. A fresh-context rubric review is the highest-return phase and reproduces the verifier evidence. | p.1 verification; p.4 P4 | DeepVerifier; debate papers | **Unsupported** as stated | R10 tests decomposition, evidence retrieval, judging, and feedback. | Retain verification; do not assert comparative return on spend without measured costs and equal-resource alternatives. |
| C17. Sequential scaling has a context ceiling; therefore a continuously edited draft solves context degradation. | p.3 adaptive row; p.5 controls | 2602.18998 | **Partially supported** | R9 supports limitations of accumulated context, not this proposed remedy. | Reconstruct a bounded working context from durable evidence. Editing a document does not erase earlier conversation tokens. |
| C18. Context framing and one synthesis owner prevent conflicting worker assumptions. | p.4 P3; p.5 controls | Cognition; MAST | **Partially supported** | Engineering observations motivate the control; no prevention guarantee follows.[^6][^13] | Require explicit assumptions and compatibility checks. “Workers gather” does not eliminate judgment during retrieval. |
| C19. Tongyi reports HLE 32.9 / BrowseComp 43.4 / xbench 75 and offers ReAct/heavy modes. | p.3 emerging row | Tongyi Lab | **Supported as vendor reporting** | The originating release account contains these claims and modes.[^14] | Preserve reporting attribution. Model, mode, tools, and inference budget must accompany any comparison; download access does not establish execution cost. |
| C20. Frontier BrowseComp scores within about 1.4 points make harness design the remaining lever. | p.3 emerging row | Steel / BenchLM | **Unsupported; historical number unverifiable** | No timestamped original pair of snapshots; close mixed-setup scores do not identify causation. | Remove the inference. Reconstruct matched setup records before comparing architecture or model effects. |
| C21. Conference status ranks evidence highest; verifier evidence is the only Tier A item. | pp.1–2 §02; p.5 limitation | PDF hierarchy | **Contradicted** for publication status; **unsupported** as a quality rule | MAST has NeurIPS 2025 proceedings; the counter-case has ACL SRW 2026 proceedings.[^6][^8] | Record publication status separately from methods, applicability, independence, recency, and incentives. |
| C22. All criteria must be falsifiable, every unknown documented, and any late assumption invalidates downstream phases. | p.3 P0 | Proposed gate | **Unsupported** as an empirical rule | Normative criteria need operational definitions, not necessarily falsification; unknown unknowns cannot all be listed. | Document material known unknowns; version criteria; reopen only dependent findings after an assumption changes. |
| C23. Retrieve only against the largest impact×uncertainty gap. | p.3 P2 | Proposed rule | **Unsupported** as an optimum | No cited comparison validates this allocation rule. | Use a transparent priority heuristic with reserved exploration for missing alternatives and disconfirming evidence. |
| C24. Every round must change the draft, but stop after two unchanged rounds. | p.3 P2; p.4 P5 | Proposed gates | **Contradicted internally** | Literal P2 compliance prevents satisfying P5. | Permit logged null findings. Separate evidence gain from wording changes; use a saturation checkpoint, not forced edits. |
| C25. Depth one makes parallel work bounded; reject parallelism whenever serial retrieval is cheaper. | p.4 P3 | Proposed limits | **Unsupported** as a universal rule | Depth does not cap width, calls, retries, or tokens; cost and latency are different objectives. | Bound total work and concurrency; compare feasible quality, quota use, and elapsed time. |
| C26. Only P2/P3 loop; one P4 pass suffices and defects can close through a confidence downgrade or zero-cost impossibility. | pp.3–4 protocol | Proposed gates | **Contradicted internally** as an assurance claim | Uncertainty disclosure may leave the decision dependent on an unresolved premise. | Recheck changed material claims. Keep a blocker open unless evidence or removal of decision reliance resolves it. |
| C27. Two no-change rounds demonstrate search completeness and catch under-retrieval/hedging. | p.4 P5; p.5 controls | DeepSearchQA; proposed threshold | **Unsupported** | The benchmark measures set outcomes; it does not validate this stopping detector.[^15] | Require search-space coverage and varied search routes; report unobservable recall honestly. |
| C28. The protocol costs 2–4×; verifier 1.3–2×, debate 3–8×, hierarchy 15×+. | pp.2–4 cost labels | Unspecified derivation | **Unsupported** | No common baseline, accounting method, workload, or measured ledger is provided. | Replace multipliers with measured or explicitly estimated resource use. |
| C29. Existing research subscriptions, two vendors, free APIs, and open weights make the protocol free. | p.4 §05 | Resource suggestions | **Partially supported conditionally** | Zero added expenditure depends on actual entitlement, quotas, tools, compute, and terms. | Verify the resource envelope first. Do not infer any of these resources are available. |
| C30. Two vendors’ reports become legitimate independent cross-checks of each other. | p.4 §05 | Proposed ensemble | **Unsupported** as an independence guarantee | Vendor diversity can coexist with shared evidence and correlated mistakes. | Separate model diversity, prompt isolation, and independent evidence origins; independently examine consequential claims. |
| C31. The cited coding study examines representation, selection, and reuse; DeepResearch Bench supplies RACE/FACT evaluation. | p.6 bibliography | 2604.16529; 2506.11763 | **Supported** as descriptions | The sources contain these methods; neither evaluates the PDF’s complete protocol.[^16][^17] | Preserve this limited role. Do not import coding gains or replace factual review with report-quality scores. |
| C32. The roadmap supplies a static/dynamic workflow taxonomy. | p.6 bibliography | 2506.18096 | **Supported** as a description | The survey provides the taxonomy; it is not a controlled architecture comparison.[^22] | Use it for description and discovery, without assigning it causal weight in method selection. |

## 4. Study conditions and quantitative corrections

**R1 — Single-agent comparison.** Tran and Kiela compare FRAMES and four-hop MuSiQue with Qwen3-30B, R1-Distill-70B, and Gemini 2.5 variants. Budgets are 100, 500, 1,000, and 2,000 thinking tokens, excluding prompts and final answers. At 500 requested tokens on FRAMES, Gemini 2.5 Pro scores 0.600 for SAS versus 0.660 for Sequential and Debate. This is a counterexample to literal score dominance, not proof of significant MAS superiority. API budget artifacts, answer judging, and task scope constrain the interpretation. The April 11 v2 was available before the cutoff.[^4]

**R2 — Anthropic engineering comparison.** The 90.2% reported improvement compares an Opus 4 lead with Sonnet 4 subagents against single-agent Opus 4 on an internal research evaluation. The same article reports approximately 4× chat tokens for agents and 15× for multi-agent systems. Neither benchmark size, complete per-task records, nor equal-token controls accompany the headline comparison. The two token multipliers share chat as their reference; treating either as a transferable research cost ratio is unwarranted.[^5]

**R3 — TTD-DR.** Table 1 reports 74.5% pairwise preference wins on DeepConsult. HLE-Search is 33.9 versus 29.1, HLE-Full 34.3 versus 26.6, and GAIA 69.1 versus 67.4. The Google ADK system uses Gemini 2.5 Pro and Google search grounding, with up to 20 retrieval/refinement steps. HLE-Search is an author-selected 200-question subset; long-form judging uses Gemini 1.5 Pro calibrated against human comparisons. External systems use different default models. The ablations add self-evolution and retrieval-driven revision; they do not isolate “write an unsupported draft before all planning” at matched total cost.[^1] The originating engineering account also explicitly retains plan generation and multiple workflow components.[^2]

**R4 — Positive compute-efficiency counter-case.** Wunderlich and colleagues compare self-consistency, self-refinement, debate, and mixture-of-agents on 1,000-example samples of MMLU-Pro/BBH, using 4-bit Llama 3.1 8B/70B. The paper reports +1.3 and +2.7 accuracy points for debate/MoA over self-consistency at comparable estimated compute. Compute is modeled from FLOPs and memory transfer, not measured service latency. Individual intervals overlap; configurations were selected from a performance frontier. These are credible alternatives to test, not proof that MoA generalizes to research with tools. Publication is ACL 2026 Student Research Workshop.[^8]

**R5 — Task–architecture interaction.** Kim and colleagues’ April v3 covers 260 configurations, six benchmarks, five architectures, and three model families. It reports standardized tools/prompts and matched reasoning-token budgets, with differing iteration arrangements. Its within-domain results favor different architectures for decomposable versus sequential tasks. Small 20-instance coding/terminal subsets and uncertainty over cross-domain prediction limit generalization. Budget reporting does not establish equality of every real deployment cost. Its fitted thresholds are study-specific observations, not routing laws.[^9]

**R6 — Failure taxonomy.** MAST contains 1,642 traces across seven frameworks. Taxonomy development used close analysis of approximately 150 traces; κ=0.88 describes expert agreement during taxonomy development. Automated annotation agreement is separately reported at 0.77, with 0.79 on additional systems. The study offers failure diagnosis and intervention case studies, not a hierarchy-depth experiment. Its final publication is in NeurIPS 2025’s Datasets and Benchmarks track.[^6]

**R7 — Recursive orchestration.** LangChain’s July 1 account reports 19 AgNews/OOLONG examples run three times at 128k: 0.44 without a REPL and 0.79 with one. Numeric answers receive partial credit, so 0.79 is not 79% exact accuracy. The author calls the evaluation a proof of concept and distinguishes recursive agents from the original RLM formulation. Refusal is illustrated, not universal: the nonzero aggregate baseline itself precludes reading the result as every run refusing. Full model/budget details are insufficient for an architecture-only estimate.[^11]

**R8 — Debate evidence is conditional.** Chen and colleagues test error detection and additional reasoning/safety tasks, including heterogeneous model pairs. Their approximately 15-point degradation pertains to an error-detection comparison, not a universal research-accuracy loss; collaborative debate provides positive counterevidence.[^7] Bertalanič and Fortuna test ten homogeneous 7–8B agents, three rounds, GSM-Hard/MMLU-Hard, with self-correction and unrelated-rationale controls. Peer ordering and token overhead remain design-specific; their study does not evaluate frontier evidence-retrieving reviewers.[^10]

**R9 — Scaling and the verification gap.** General AgentBench combines search, reasoning, coding, and tool use across ten models, with sampling up to K=4 and sequential contexts up to 196k. Its approximately 50% average pass@K improvement is relative and assumes ideal selection. Actual selection often saturates; a GPT-5 external verifier can underperform a model’s own judgment. Its context ceiling is observed under its tool/context/continuation setup, not a universal limit or a test of in-place document editing.[^20]

**R10 — DeepVerifier.** The ACL paper uses decomposition, a trajectory synopsis, follow-up retrieval through CK-Pro, a judge, and iterative feedback. Table 2’s rejection-F1 values are 73.17, 61.54 without decomposition, and 25.00 without verification: differences of **11.63** and **48.17 points**. With Claude 3.7, Table 3 gives GAIA-Web **+12.22 best / +11.11 final points**, and GAIA-Full **+7.90 / +6.71**. Table 4 gives XBench **+6 / +3**. GPT-4.1 gains are smaller. Later feedback can reverse correct answers. The study does not measure a universally best verification return per token or establish full-draft isolation as the active ingredient.[^3]

### Independent evidence origins

Counting documents would inflate support. The following counts concern distinct experimental/reporting origins, not proven statistical independence:

| Method question | Distinct origins used | What the count permits |
|---|---|---|
| Complete PDF P0–P5 protocol | **0** direct evaluations | Its end-to-end reliability and cost remain unestablished. |
| Draft-driven long-form research gains | **1** TTD-DR origin | Paper and Google blog are one result, not replication. |
| DeepVerifier improvement | **1** origin | Preprint, ACL paper, and repository are one research program. |
| Architecture/budget comparisons central to selection | **4**: Tran/Kiela, Wunderlich et al., Kim et al., Chen et al. | They test different tasks and controls; several reuse benchmark families. Their results cannot be pooled as independent votes. |
| Evidence for separating verification answers from preceding responses | **2** relevant but different origins: CoVe and Cost of Consensus | CoVe directly varies access to prior answers; the latter concerns homogeneous peer debate. Neither establishes independence of two vendors’ reports. |
| Vendor breadth advantage | **1** Anthropic internal origin | Repeated quotations of the 90.2% figure add no corroboration. |
| OOLONG 0.44→0.79 claim | **1** LangChain harness experiment | The original RLM work is not a second measurement of that specific comparison. |

MAST, General AgentBench, DeepSearchQA, and DeepResearch Bench are additional distinct diagnostic/evaluation origins. Their reuse of models, benchmark components, and LLM judges means that distinct papers should not be treated as fully independent empirical replications. Source count alone does not determine confidence.

## 5. Explicit adjudications

| Question | Adjudication |
|---|---|
| Is sequential reasoning plus bounded parallel retrieval and isolated verification a general default? | **A defensible initial policy, not an empirically established general winner.** Begin with one accountable synthesis process when dependencies are strong; make parallelism and independent checking responsive to the task. Retrieval-only parallelism is an optional restriction, not a law. |
| Are architecture effects distinguishable from model, tokens, tools, and evaluation? | **Partly, within controlled studies.** Reasoning-token matching is weaker than full resource matching. Different models, hidden reasoning, prompt overhead, tool calls, retries, and judges can change the result. Deployment comparisons must report these separately. |
| Is draft-first broadly supported? | **Only conditionally.** A tentative draft can expose gaps, but the evidence does not mandate a fully populated report from prior knowledge. In unfamiliar or evidence-sensitive work, a question map and source discovery before substantive drafting avoid embedding unsupported starting assumptions. |
| Is the PDF’s verification operationally specified and supported? | **No.** A rubric is listed, but source access, decomposition, blind checks, severity definitions, correction/recheck loops, and false-acceptance handling are absent. Fresh conversation state is not equivalent to an independent factual test. |
| Are authority, quality, independence, recency, and incentives assessed separately? | **No.** Publication tiers and occasional vendor caveats conflate these dimensions. Use the separate appraisal fields below. |
| Are the no-change and saturation rules coherent? | **No under their literal wording.** Under a charitable reading, no-change causes reprioritization, but the protocol still fails to define the counter, coverage, and relation to verification. Replace both rules. |
| Which numeric limits are findings and which are heuristics? | **Benchmark outcomes are observations; study budgets are experimental settings; protocol caps are design rules.** The cost multipliers have no documented derivation. None of the proposal’s operational thresholds is demonstrated optimal. |
| When should another method be used? | **When the task’s dependencies, evidence needs, context volume, or available feedback favor it.** The alternatives in Section 7 are conditional choices, not a new universal ranking. |

## 6. Defects ranked by reliability impact

| Rank | Defect | Consequence | Required remedy |
|---|---|---|---|
| 1 — Critical | Critical uncertainty can be “closed” by relabeling it; no mandatory recheck after repair. | A report can pass while its decision still depends on an unsupported premise. | Distinguish disclosure from resolution; reverify modified claims and affected dependencies. |
| 2 — Critical | Compound study gains are assigned to materially different proposed interventions. | The selected method appears validated when its active components and resource requirements have changed. | Identify retained components and untested substitutions; validate the complete candidate separately. |
| 3 — High | Architecture universals and ignored counterevidence. | The protocol can select the wrong method before the actual task is characterized. | Require task-conditioned selection and a feasible comparator. |
| 4 — High | Draft-led search has no independent coverage or disconfirmation mechanism. | Missing possibilities remain invisible because only existing draft gaps drive retrieval. | Maintain a criteria/alternative map outside the prose and reserve exploratory retrieval. |
| 5 — High | Contradictory stopping criteria and undefined search coverage. | Either forced edits prolong work or repeated low-yield searches justify premature termination. | Log null evidence events; require varied routes and explicit coverage before a sufficiency claim. |
| 6 — High | Numerical misattribution, ambiguous units, and common-baseline errors. | Method selection and resource planning rest on misleading magnitudes. | Preserve dataset, unit, denominator, and peak/final distinction in a claim ledger. |
| 7 — High | Source quality is collapsed into publication tier; verification independence is asserted. | Correlated, prestigious, or commercially interested evidence can be overcounted. | Appraise independent dimensions and identify original evidence-producing events. |
| 8 — High | No implemented context or resource budget. | A “bounded” method can exhaust quotas, lose evidence, or retain contaminating history. | Bound total work, externalize evidence, and reconstruct working context explicitly. |
| 9 — Moderate | Immutable framing and broad invalidation rules. | Learning new constraints either cannot be incorporated or causes unnecessary restart. | Version framing and invalidate only affected findings, with a visible change record. |

## 7. Alternative-method assessment

| Task condition | Candidate approach | Evidence and comparative boundary |
|---|---|---|
| Unfamiliar topic; coverage and neutrality matter before an answer is formed. | Source discovery, perspective mapping, and an evidence-based outline before substantive drafting. | STORM studies research and outline construction before Wikipedia-like article generation. It uses retrieved information and perspective-guided questions, with FreshWiki and expert feedback. This is a relevant alternative to mandatory prior-only drafting, not a direct head-to-head victory over TTD-DR.[^19] |
| Tightly dependent reasoning; limited resources; all necessary evidence fits a manageable context. | One synthesis process with iterative retrieval and selective checking. | Consistent with the narrower single-agent findings. Keep a strong simple baseline; benchmark a more complex option only when a specific limitation warrants it.[^4] |
| Many independent entities, documents, or evidence channels; elapsed time matters. | Bounded parallel extraction or investigation, followed by one reconciliation step. | Anthropic’s breadth result is a relevant operational example. It is not an equal-cost causal estimate. Workers may provide explicitly provisional interpretation when extraction requires judgment.[^5] |
| Long inputs require near-exhaustive coverage or aggregation. | Programmatic partitioning, extraction, and reduction; recursion only where it adds value. | The OOLONG harness result supports testing this family. Compare it with a simpler deterministic loop or map/reduce process before crediting recursion itself.[^11] |
| Independent proposals can be evaluated against stable criteria or executable checks. | Small candidate ensembles, structured selection, or collaborative critique. | The Pareto study and collaborative-debate results oppose blanket rejection. Their gains depend on models, tasks, selection mechanisms, and available resources.[^7][^8] |
| A factual claim risks being copied into its own verification answer. | Answer-blind subquestion verification, followed by explicit comparison with the claim. | CoVe’s factored variants withhold original answers during verification. Experiments use Llama 65B with factual/list/biography tasks and do not use external retrieval for generation/verification. This supports an isolation mechanism, not contemporary long-form research certification.[^23] |
| Coding or another executable task provides useful trial feedback. | Preserve compact attempt summaries; test candidates and reuse failures rather than only polishing prose. | The cited coding paper studies structured rollout summaries, recursive selection, and refinement with actual agent harnesses. Its selector does not have ground-truth outcomes. It is a task-specific counterexample to rejecting parallel selection until a universal verification gap “closes.”[^16] |
| Decision requires systematic evidence coverage or causal inference. | Prespecified eligibility, search coverage, extraction, and study-level bias appraisal. | This follows from the task’s evidentiary requirements. The PDF’s agent benchmarks do not establish a substitute for those requirements. An agent loop can assist the work without defining its validity. |

Enumeration, reasoning, and verification are not mutually exclusive task classes. A project may need broad discovery, sequential synthesis, and separately checked decisive claims. Adaptation should follow a recorded limitation, not merely increasing the agent count.

## 8. Audited candidate protocol

This protocol is an **auditor-proposed design** informed by the bounded evidence above. Its phase definitions and gates are operational choices, not experimentally optimized thresholds. It is domain-agnostic and makes no assumption about available subscriptions, APIs, compute, or intended system architecture.

### Phase A — Frame the inquiry and establish the resource envelope

**Inputs:** the question, supplied evidence, required output, known constraints, and explicitly verified capabilities.

**Actions:** classify the inquiry—description, comparison, explanation, prediction, or decision—and specify success criteria appropriate to it. Record material known unknowns, contested terms, excluded scope, evidence cutoff, and consequences of a wrong answer. A preference or normative criterion receives an operational definition rather than a forced claim of falsifiability.

Record the execution mechanisms actually available, zero-additional-spend conditions, quota/time limits, and capabilities needed for retrieval and checking. Unknown entitlement remains unknown. A downloadable model, an advertised free service, or an existing subscription mentioned in a proposal does not establish usable access. If resource use cannot be metered precisely, name the observable proxy, such as query count, elapsed time, or remaining allowance.

**Output:** a versioned brief and resource ledger, with a hard boundary of no additional expenditure.

**Gate:** no hidden dependency on unverified paid access. Any missing capability that prevents a critical evidence check is flagged before dependent conclusions are accepted. This can yield a bounded report with blocked conclusions; it need not halt every useful read-only investigation.

### Phase B — Map questions, alternatives, and evidence

**Inputs:** the brief and supplied material.

**Actions:** extract material claims and identify plausible alternatives before endorsing one. Build a question map and preliminary source plan. Conduct a small orientation search when unfamiliarity makes a substantive draft likely to anchor the inquiry. Include a route for credible opposing evidence and a route for omitted alternatives.

A tentative full draft is optional. If used, label unsupported statements and keep them out of the evidence ledger. An outline or list of competing hypotheses is equally valid. Confidence must reflect accessible evidence, not prose fluency.

**Output:** a criteria-by-question map, alternative set, claim ledger, and documented choice of work pattern.

**Gate:** the inquiry is not defined solely by gaps in one preferred answer. Every consequential criterion has a planned evidence or uncertainty treatment.

### Phase C — Acquire and appraise evidence

**Inputs:** prioritized questions and the remaining resource envelope.

**Actions:** prioritize by decision consequence, uncertainty, dependency, and the likelihood that feasible evidence could change the conclusion. Use ordinal judgments with brief reasons unless calibrated probabilities exist. Do not present an arbitrary impact×uncertainty score as a validated utility function.

Retrieve primary sources and exact versions where possible. Preserve source locations, necessary passages or data, relevant conditions, and negative findings. Search snippets support discovery, not full verification. Inaccessible primary text receives an explicit access label; a secondary report is not silently promoted to primary evidence.

Parallel work is permitted only when subtasks can be specified and reconciled within budget. Set concurrency, total calls, per-task limits, retries, and permitted depth before dispatch. Depth one is a reasonable initial simplification, explicitly a heuristic; it does not itself bound cost. Workers receive the relevant framing and return sources, observations, assumptions, and any provisional interpretations. One synthesis owner resolves conflicts.

**Output:** evidence records and a search log, including zero-yield searches.

**Gate:** consequential findings have a traceable source and bounded interpretation. Lack of new evidence is a valid result and never requires a cosmetic claim or confidence change.

### Separate source-appraisal fields

| Field | Assessment question | Required treatment |
|---|---|---|
| Authority/proximity | Is this the original record or a party with relevant firsthand knowledge? | Identify the source’s competence for this claim. A provider is authoritative about what it reported, not automatically about universal superiority. |
| Methodological quality | Are comparisons controlled and measurements valid? | Record sampling, baseline, budgets, harness, uncertainty, judge quality, and missing checks. |
| Independence | Does this add a new evidence-producing event? | Link republications, shared datasets, overlapping experiments, and known common dependencies. |
| Recency and version | Does the evidence apply to the relevant time and version? | Separate event date, publication date, revision date, and access date. |
| Incentives | What interests could affect design, selection, or reporting? | Record funding, ownership, commercial benefit, and evaluation design interests without treating them as automatic disqualification. |
| Directness/applicability | How closely does the tested intervention match the proposed use? | State the transfer gap: task, model, tools, resource envelope, or output type. |
| Access and reproducibility | Was full evidence read and can the result be inspected or rerun? | Distinguish abstract, full text, data, code, and an actual independent replication. |

Do not collapse these fields into a single prestige score. A primary vendor report can have high proximity and low independent replication; a reviewed paper can have poor task applicability.

### Phase D — Synthesize and challenge

**Inputs:** appraised evidence and the question map.

**Actions:** revise the synthesis using supported findings; retain competing explanations and unresolved disagreements. Distinguish empirical observation, interpretation, and proposed rule. Link each recommendation to its consequential premises. Recalculate quoted numeric changes and preserve units and denominators.

For every preferred method, state the strongest feasible alternative, the strongest evidence against the preference, and a condition that would change the choice. Reopen the framing if a material assumption changes, recording which dependent findings require review.

**Output:** a candidate report, a claim-to-source map, and a contradiction/dependency register.

**Gate:** no recommendation is stronger than its weakest necessary premise without explicit qualification. Conflicting evidence is resolved by conditions or left visibly unresolved, never by vote count.

### Phase E — Verify consequential claims

**Inputs:** the fixed question and criteria, candidate report, source records, and a descriptive activity synopsis. Private internal reasoning is not required.

**Actions:** perform two distinct checks:

1. **Source fidelity:** confirm the cited source actually says what is attributed, with the correct date, setting, metric, and limitation. Recalculate quantities from the source table when possible.
2. **Claim validity:** test whether that source is adequate for the conclusion, whether credible counterevidence exists, and whether dependencies or alternatives were missed.

For a decisive factual check, formulate an open verification question and, where the environment permits, answer it in a separate context without the proposed answer or advocate’s rationale. The question must retain enough task framing to be meaningful. Then compare the independent answer and evidence with the draft. Source-fidelity checking may necessarily expose the claim; record that distinction rather than calling all checks blind.

A different model or vendor may add diversity, but is neither mandatory nor sufficient. Record which independence was achieved: answer/context isolation, independently located evidence, and model diversity. If no separate context is available, conduct the evidence check and disclose the reduced isolation.

Inspect every consequential claim and recommendation premise. Lower-impact prose can receive a documented risk-based sample. Expand that sample if a material error appears. This full coverage of consequential claims is an assurance requirement, not a benchmark-derived threshold.

**Output:** a defect ledger with claim ID, evidence, severity, proposed correction, and disposition.

**Gate:** a critical defect blocks the affected recommendation. A critical defect is one that could reverse a method choice, invalidate a necessary premise, or breach a hard constraint. A confidence downgrade only resolves it if the delivered conclusion is changed so it no longer relies on that premise.

### Phase F — Correct and recheck

**Inputs:** the defect ledger and affected claim dependencies.

**Actions:** obtain missing evidence, correct the claim, narrow the conclusion, remove the dependency, or preserve it as an unresolved blocker. Recheck modified consequential claims and their dependent recommendations. If findings alter task framing or candidate selection, return to the relevant earlier phase.

**Output:** a revised report and a disposition record distinguishing corrected, qualified, removed, and unresolved findings.

**Gate:** no known critical defect is hidden under a “closed” label. Repeated verification without new evidence or a new diagnostic is stopped as nonproductive; budget exhaustion is recorded separately from assurance.

### Phase G — Stop with an explicit completion status

**Inputs:** coverage map, evidence/search log, defect ledger, and remaining resources.

Stop under one of the following statuses:

| Status | Required conditions | Delivered conclusion |
|---|---|---|
| Sufficiently supported within scope | Material criteria addressed; consequential claims checked; counterevidence considered; no known decision-blocking defect; coverage and remaining uncertainty recorded. | A qualified candidate conclusion within the investigated scope. |
| Bounded incomplete | Time, allowance, access, or feasible search routes exhausted before an essential issue is resolved. | Useful findings plus the exact blocked recommendation, missing evidence, and next resolving action. |
| Reframe required | The question is underdetermined, criteria conflict, or a newly discovered assumption changes what must be answered. | A corrected problem statement and the findings that remain valid. |

Use **two consecutive low-yield coverage sweeps over meaningfully different search routes** as a practical trigger to reassess continued searching. This is a heuristic, not proof of completeness. A sweep records its queries, evidence channels, criteria covered, and new independent information. Repeated searches through the same ranking channel do not count as independent coverage.

For a finite enumerated corpus, reconcile processed items against its manifest and record failed items. For open-web research, unknown recall remains unknown. New entities are not the only useful gain: corroboration, contradiction, a corrected date, or better boundary conditions can matter. Conversely, additional wording is not evidence gain.

### Context and effort controls across phases

Maintain three distinct records: **current synthesis**, **durable evidence/decision records**, and **a search/activity log**. The synthesis is concise and replaceable; evidence provenance and earlier dispositions remain inspectable. When rebuilding working context, include the current brief, verified claim state, unresolved contradictions, and source pointers. Preserve exact source material outside the active context where the available environment supports it.

A document edit does not remove conversation history. Actual context reconstruction requires a new context or an explicit supported compaction mechanism. Inspect the reconstructed state for lost qualifications before continuing. Treat retrieved instructions as source content, never as changes to the research brief.

Set a retrieval allowance, a reserved verification allowance, and a bounded repair allowance during Phase A; choose their sizes from the actual task and resource limits. Increase effort when a necessary premise is weak, a contradiction could reverse the conclusion, or source coverage is demonstrably incomplete. Decrease effort for peripheral claims and duplicate evidence. Stop before the resource envelope is breached, even if that means delivering an incomplete result.

### Numeric-rule register

| Quantity | Classification | Operational meaning |
|---|---|---|
| Published scores, F1 differences, token ratios, and observed context ceilings | Empirical observations under named conditions | Do not transfer them as guaranteed gains or costs. |
| Study settings: K=4, ten agents, particular round counts, 20 TTD steps, 100–2,000 thinking tokens | Experimental configuration | These are not optimal settings for a new task. |
| Depth-one initial cap; two low-yield sweeps; risk-based sampling | Practical heuristics | Declare and revise them when evidence or constraints warrant it. |
| No additional expenditure; checking all consequential claims; no unresolved decision blocker for a supported conclusion | Normative constraints/assurance requirements | These define acceptable delivery, not measured success probabilities. |
| Proposal’s 2–4× total cost and other family multipliers | Unsupported estimates | Remove until measured against an explicit baseline. |

### Validation needed before operational adoption

Compare the candidate with a strong simpler baseline and the most relevant alternative on the same representative tasks. Hold model/version, tools, source access, and observable budget constant where possible; separately report unavoidable differences. Evaluate factual/source accuracy, critical omissions, false acceptance of defects, unnecessary corrections, completion status, resource use, and elapsed time.

Include cases with contradictory sources, incomplete evidence, and deliberately identifiable errors. Assess both false acceptance and damage to previously correct conclusions. Repeat variable cases where feasible and preserve paired results; a small pilot demonstrates feasibility, not broad superiority. Select sample size and acceptance thresholds in advance according to consequence and available resources. If such validation is unavailable at zero added expenditure, retain candidate status and record the adoption blocker.

## 9. Decision record

| Proposal element | Disposition | Reason |
|---|---|---|
| Methodology-only scope and no inferred system requirements | Retained | Prevents premature domain/architecture assumptions. |
| Zero-additional-spend constraint | Retained and operationalized | Requires an actual resource envelope; it does not imply any subscription or compute access. |
| One accountable synthesis process | Retained conditionally | Useful for coherent dependent interpretation; not equivalent to forbidding all other reasoning work. |
| Iterative research and revision | Retained | Supports incremental evidence integration without committing to TTD-DR equivalence. |
| Mandatory unsupported full draft | Replaced | Permit source-first question mapping or an explicitly tentative draft. |
| Parallel retrieval | Retained with explicit work limits | Depth alone is insufficient; allow provisional worker judgments and central reconciliation. |
| Rubric-based verification | Retained and expanded | Add primary evidence, decomposed checks, independence records, severity, and rechecking. |
| Universal rejection of hierarchy, debate, or larger sampling | Rejected | Positive results and task conditions make categorical exclusions unsound. |
| Publication-tier hierarchy | Replaced | Separate methods, directness, independence, recency, incentives, and access. |
| Forced change and two-round proof of saturation | Rejected | Replace with null-result logging, coverage checks, and distinct completion states. |
| Cost multipliers and automatic two-vendor independence | Rejected | No valid general accounting or independence inference is supplied. |
| Finalized protocol designation | Withheld | This deliverable is an audited candidate awaiting review and validation. |

## 10. Open issues and resolving evidence

| Open issue | Effect on the verdict | What would resolve it |
|---|---|---|
| Original compilation provenance and search history | Limits reconstruction of what was actually consulted; does not negate pre-cutoff corrections. | Timestamped source/version log or original research export. |
| Anthropic’s internal comparison cannot be independently reproduced from the article | Limits the magnitude and architecture-causality claims. | Evaluation tasks, per-run outputs, costs, model settings, and controlled comparisons. |
| Exact August 30 Steel/BenchLM snapshots and BenchLM citation identity | Historical 1.4-point claim remains unverifiable. | Direct original URLs, archived snapshots, and underlying submission records. |
| Complete TTD-DR component/resource accounting and independent replication | Prevents assigning the reported gain to the proposed simplified loop. | Released reproducible implementation/data and a matched-budget component ablation. |
| DeepVerifier’s exact yield under a new model, task, and budget | Critical adoption blocker; fresh-context review cannot inherit its reported performance. | Calibrated evaluation with known defects and clean cases, including repair regressions. |
| ACM final version of Cost of Consensus | Publisher page access returned 403; accessible arXiv text was used. | Accessible publisher full text and publication metadata. The linked DOI alone is not a completed comparison of versions. |
| Recursive proof-of-concept configuration and historical version | Limits model/budget attribution and exact as-of dating of current page content. | Frozen harness, prompts, run logs, model IDs, and dated source revision. |
| Execution resources and candidate performance | Critical adoption blocker; neither feasibility nor total cost is established for an unspecified environment. | Verified entitlement/limits and a bounded, paired pilot. |

**Post-cutoff evidence:** Saeed and Razniewski’s September 1 LLMpedia demonstrator separates supported, refuted, and insufficient claims and documents sampled verification and judge dependence. It reinforces the usefulness of recording insufficient evidence. Its own scope excludes completeness and overall article quality; it is not a controlled comparison of the audited workflows. The larger findings belong to a companion research origin and are not counted as a separate replication.[^21]

The revised gates preserve unresolved decision blockers explicitly and direct them to an incomplete or reframed result. **Critical evidence gaps nevertheless remain before operational adoption**, especially end-to-end validation and verifier calibration. No claim of final approval is made.

## 11. Sources and access records

All sources below were accessed **12 September 2026**. “Full text” means the accessible paper or originating article text, not independent reproduction of its experiments. Versions are fixed where practical. Preprint status means that is the verified accessible record; it does not assert that no other publication exists. Repositories and lab accounts are not counted as independent replications of their associated papers.

[^1]: Rujun Han, Yanfei Chen, Zoey CuiZhu, Lesly Miculicich, Guan Sun, Yuanjun Bi, Weiming Wen, Hui Wan, Chunfeng Wen, Solène Maître, George Lee, Vishy Tirumalashetty, Emily Xue, Zizhao Zhang, Salem Haykal, Burak Gokturk, Tomas Pfister, and Chen-Yu Lee. [Deep Researcher with Test-Time Diffusion](https://arxiv.org/html/2507.16075v1). July 21, 2025; arXiv preprint 2507.16075v1. Full text; methods, Tables 1–2, evaluation and limitations. Public replication artifacts sufficient to reproduce the comparison were not independently established.

[^2]: Rujun Han and Chen-Yu Lee, Google Research. [Deep researcher with test-time diffusion](https://research.google/blog/deep-researcher-with-test-time-diffusion/). September 19, 2025. Full originating engineering article; same experimental origin as [1].

[^3]: Yuxuan Wan, Tianqing Fang, Zaitang Li, Yintong Huo, Wenxuan Wang, Haitao Mi, Dong Yu, and Michael R. Lyu. [Inference-Time Scaling of Verification: Self-Evolving Deep Research Agents via Test-Time Rubric-Guided Verification](https://aclanthology.org/2026.findings-acl.1243/). Findings of ACL 2026, July 2–7, pp.24822–24835. [Full publisher PDF](https://aclanthology.org/2026.findings-acl.1243.pdf), especially §§4–7 and Tables 2–5. [Preprint record](https://arxiv.org/abs/2601.15808): January 22, 2026; v2 April 29. Conference status confirmed; not an independent replication of the preprint.

[^4]: Dat Tran and Douwe Kiela. [Single-Agent LLMs Outperform Multi-Agent Systems on Multi-Hop Reasoning Under Equal Thinking Token Budgets](https://arxiv.org/html/2604.02460v1). April 2, 2026; arXiv preprint. [April 11 v2](https://arxiv.org/html/2604.02460v2) also checked. Full text; §4, Table 1 and budget/context caveats. The supplied PDF links v1.

[^5]: Jeremy Hadfield, Barry Zhang, Kenneth Lien, Florian Scholz, Jeremy Fox, and Daniel Ford, Anthropic. [How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system). June 13, 2025. Full originating engineering article; internal evaluation, token accounting, and operational observations. Raw evaluation data and complete harness are unavailable in the article.

[^6]: Mert Cemri, Melissa Z. Pan, Shuyi Yang, Lakshya A. Agrawal, Bhavya Chopra, Rishabh Tiwari, Kurt Keutzer, Aditya Parameswaran, Dan Klein, Kannan Ramchandran, Matei Zaharia, Joseph E. Gonzalez, and Ion Stoica. [Why Do Multi-Agent LLM Systems Fail?](https://proceedings.neurips.cc/paper_files/paper/2025/hash/b1041e52d3be19f0a9bc491657488e4a-Abstract-Datasets_and_Benchmarks_Track.html). NeurIPS 2025, Datasets and Benchmarks Track; publication confirmed. [Full arXiv v3](https://arxiv.org/html/2503.13657v3), October 26, 2025; first submitted March 17. Taxonomy construction, annotation, and intervention sections consulted.

[^7]: Yongqiang Chen, Gang Niu, James Cheng, Bo Han, and Masashi Sugiyama. [When and Why Does Multi-Agent Debate Fail and Does It Really Underperform?](https://arxiv.org/html/2510.20963v2). First submitted October 23, 2025; v2 July 14, 2026. Full preprint text, experiments and ablations. [Author publication record](https://www.ms.k.u-tokyo.ac.jp/sugi/publications.html) lists a July 10 ICML 2026 workshop presentation; this is not a claim of ICML main-track publication.

[^8]: Florian Valentin Wunderlich, Lars Benedikt Kaesberg, Jan Philip Wahle, Terry Ruas, and Bela Gipp. [Multi-Agent Reasoning Improves Compute Efficiency: Pareto-Optimal Test-Time Scaling](https://aclanthology.org/2026.acl-srw.1/). ACL 2026 Student Research Workshop, July 2026, pp.1–14; publication confirmed. [Full preprint](https://arxiv.org/html/2605.01566v1), May 2, 2026; methods, limitations, and compute accounting consulted.

[^9]: Yubin Kim, Ken Gu, Chanwoo Park, Chunjong Park, Samuel Schmidgall, A. Ali Heydari, Yao Yan, Zhihan Zhang, Yuchen Zhuang, Yun Liu, Mark Malhotra, Paul Pu Liang, Hae Won Park, Yuzhe Yang, Xuhai Xu, Yilun Du, Shwetak Patel, Tim Althoff, Daniel McDuff, and Xin Liu. [Towards a Science of Scaling Agent Systems](https://arxiv.org/html/2512.08296v3). First submitted December 9, 2025; v3 April 8, 2026. Full preprint text; experiment controls, limitations and Appendix E. Added counterevidence, available before the cutoff.

[^10]: Blaž Bertalanič and Carolina Fortuna. [The Cost of Consensus: Isolated Self-Correction Prevails Over Unguided Homogeneous Multi-Agent Debate](https://arxiv.org/html/2605.00914v1). April 29, 2026; accessible arXiv v1. Full text; controlled homogeneous-team setup. [Linked ACM DOI](https://dl.acm.org/doi/10.1145/3786335.3813137) returned 403; final publisher text/version comparison remains unresolved.

[^11]: Sydney Runkle, LangChain. [How to Use RLMs in Deep Agents](https://www.langchain.com/blog/how-to-use-rlms-in-deep-agents). July 1, 2026, byline/date on the originating article. Full article and OOLONG table accessed; page is mutable. This result belongs to LangChain’s recursive-agent harness proof of concept, not directly to the original RLM paper.

[^12]: Lance Martin. [Learning the Bitter Lesson](https://rlancemartin.github.io/2025/07/30/bitter_lesson/). July 30, 2025. Full originating author account of Open Deep Research’s workflow changes. [Project README](https://github.com/langchain-ai/open_deep_research) also accessed; mutable current repository. Used to distinguish centralized writing from retained multi-agent context gathering.

[^13]: Walden Yan, Cognition. [Don’t Build Multi-Agents](https://cognition.com/blog/dont-build-multi-agents). June 12, 2025; page metadata indicates modification March 15, 2026. Full engineering essay. Context/coordination observations, not a controlled general architecture comparison.

[^14]: Tongyi DeepResearch team. [Tongyi DeepResearch: A New Era of Open-Source AI Researchers](https://tongyi-agent.github.io/blog/introducing-tongyi-deep-research/). September 16, 2025. Full originating release account; model results and ReAct/IterResearch/Research-Synthesis descriptions. Scores remain vendor-reported; no independent replication is claimed.

[^15]: Nikita Gupta, Riju Chatterjee, Lukas Haas, Connie Tao, Andrew Wang, Chang Liu, Hidekazu Oiwa, Elena Gribovskaya, Jan Ackermann, John Blitzer, Sasha Goldshtein, and Dipanjan Das. [DeepSearchQA: Bridging the Comprehensiveness Gap for Deep Research Agents](https://arxiv.org/html/2601.20975v1). January 28, 2026; arXiv preprint. Full text; set-based metrics, error analysis, and static-web/process-observability limitations. No validation of a two-round saturation rule.

[^16]: Joongwon Kim, Wannan Yang, Kelvin Niu, Hongming Zhang, Yun Zhu, Eryk Helenowski, Ruan Silva, Zhengxing Chen, Srinivasan Iyer, Manzil Zaheer, Daniel Fried, Hannaneh Hajishirzi, Sanjeev Arora, Gabriel Synnaeve, Ruslan Salakhutdinov, and Anirudh Goyal. [Scaling Test-Time Compute for Agentic Coding](https://arxiv.org/html/2604.16529v1). April 16, 2026; arXiv preprint. Full text available; representation, selection, reuse, harness and ground-truth-access conditions consulted. No transfer of its coding gains to generic research is asserted.

[^17]: Mingxuan Du, Benfeng Xu, Chiwei Zhu, Xiaorui Wang, and Zhendong Mao. [DeepResearch Bench: A Comprehensive Benchmark for Deep Research Agents](https://arxiv.org/html/2506.11763v1). June 13, 2025; arXiv preprint. [Originating project](https://deepresearch-bench.github.io/) and full text accessed. RACE addresses report quality and FACT citation/information measures; neither is a complete guarantee of truth or completeness.

[^18]: Steel. [BrowseComp Leaderboard](https://leaderboard.steel.dev/leaderboards/browsecomp/). Accessed live page lists update date September 4, 2026. Used only to establish the page’s current identity and snapshot limitation. The supplied PDF’s BenchLM item was not independently resolved to its exact original record; no link is invented.

[^19]: Yijia Shao, Yucheng Jiang, Theodore A. Kanell, Peter Xu, Omar Khattab, and Monica S. Lam. [Assisting in Writing Wikipedia-like Articles From Scratch with Large Language Models](https://aclanthology.org/2024.naacl-long.347/). NAACL 2024 main long papers, June 16–21, pp.6252–6278. [Full publisher PDF](https://aclanthology.org/2024.naacl-long.347.pdf), methodology, comparison setup, citation assessment, and limitations consulted. Added pre-cutoff alternative.

[^20]: Xiaochuan Li, Ryan Ming, Pranav Setlur, Abhijay Paladugu, Andy Tang, Hao Kang, Shuai Shao, Rong Jin, and Chenyan Xiong. [Benchmark Test-Time Scaling of General LLM Agents](https://arxiv.org/html/2602.18998v1). February 22, 2026; arXiv preprint. Full text; §§3–4 and context/budget/selection conditions consulted. Pass@K and selected-output performance are distinct endpoints.

[^21]: Muhammed Saeed and Simon Razniewski. [LLMpedia: Browsing, Verifying, and Comparing the Parametric Encyclopedic Knowledge of LLMs](https://arxiv.org/html/2609.01182v1). September 1, 2026; arXiv demonstrator preprint. Full text; claim-verification description and limitations. **Post-cutoff supplement only**; companion-study findings are not independently replicated here.

[^22]: Yuxuan Huang, Yihang Chen, Haozheng Zhang, Kang Li, Huichi Zhou, Meng Fang, Linyi Yang, Xiaoguang Li, Lifeng Shang, Songcen Xu, Jianye Hao, Kun Shao, and Jun Wang. [Deep Research Agents: A Systematic Examination And Roadmap](https://arxiv.org/html/2506.18096v2). First submitted June 22, 2025; v2 September 3, 2025. Full survey available; workflow taxonomy used descriptively, not as causal evidence of superiority.

[^23]: Shehzaad Dhuliawala, Mojtaba Komeili, Jing Xu, Roberta Raileanu, Xian Li, Asli Celikyilmaz, and Jason Weston. [Chain-of-Verification Reduces Hallucination in Large Language Models](https://aclanthology.org/2024.findings-acl.212/). Findings of ACL 2024, August 11–16, pp.3563–3578. [Full publisher PDF](https://aclanthology.org/2024.findings-acl.212.pdf); isolation variants, task/model setup, tool-use exclusion, and inference overhead. Added pre-cutoff evidence for a specific verification mechanism.
