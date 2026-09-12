# Deep Research Method

**Type:** Executable protocol
**Scope:** Any research task where the cost of being confidently wrong exceeds the cost of the extra passes
**Executor:** Human, agent, or human-supervised agent loop
**Status:** v1.0

---

## 1. Purpose

Deep research is not "search more." It is a gated pipeline that converts an underspecified question into a defensible claim set with attached confidence and a visible audit trail.

The method exists to defeat four specific failure modes:

| Failure mode | Mechanism | Gate that catches it |
|---|---|---|
| Premature convergence | First plausible answer becomes the answer | P4 Adversarial Pass |
| Consensus laundering | Ten sources, one origin | P2 Source Hierarchy |
| Recency blindness | Stale fact treated as current | P3 Recency Decay |
| Unfalsifiable output | Claim written so it cannot be wrong | P0 Falsifiability Gate |

If a research task cannot fail any of these four ways, do not run this method. Run a search and move on.

---

## 2. Preconditions — Gate 0

Do not enter P1 until all four are written down:

1. **Decision served.** What action changes based on the answer. If no action changes, the research is entertainment — stop.
2. **Falsifiable claim shape.** The form the answer will take, stated so it could be proven wrong. "X is better than Y for Z under constraint C" — not "insights about X."
3. **Stop condition.** The evidence state at which you stop. Defined before you start, or you will stop when you get tired.
4. **Budget.** Number of source fetches, wall-clock, or compute cycles. Unbounded research is a failure state, not thoroughness.

**Gate 0 fails open.** Skipping it is the single highest-frequency cause of wasted research effort.

---

## 3. Phase Model

### P1 — Landscape Mapping

Breadth before depth. Objective is not answers; it is **vocabulary and entity capture**.

- Run 3–5 deliberately divergent queries, not five rephrasings of one.
- Harvest: domain terms, named entities, canonical sources, dominant framings, the dissenting framing.
- Output: an entity/term list and a list of the 2–4 positions that exist in the space.

**Exit criterion:** You can name the disagreement. If everything you found agrees, you have not mapped the landscape — you have found one echo chamber.

### P2 — Source Acquisition

Fetch, do not skim. Snippets are lossy and systematically biased toward whatever the aggregator's headline said.

**Source hierarchy (descending authority):**

| Tier | Source class | Treatment |
|---|---|---|
| T1 | Primary: spec, filing, source code, dataset, official docs, the paper itself | Citable alone |
| T2 | Direct institutional: vendor blog, gov site, standards body | Citable alone, check incentive |
| T3 | Expert secondary: peer review, credentialed analysis | Citable with attribution |
| T4 | Aggregator/journalism | Lead only — trace to T1/T2 before citing |
| T5 | Forum, social, SEO content | Signal for what to check; never evidence |

**Provenance rule:** Count independent origins, not documents. Five T4 articles derived from one press release is one source, not five.

### P3 — Evidence Grading

Every retained claim gets three attributes before it enters synthesis:

- **Tier** (T1–T5 above)
- **Recency status** — Live (verified current), Dated (true as of date D, decay unknown), Stale (superseded or unverifiable)
- **Incentive** — who benefits if this claim is believed

**Recency decay is domain-specific.** Software versions, pricing, org leadership, and policy decay in weeks. Mathematics does not decay. Assign the decay rate explicitly; do not inherit it from vibes.

**Conflict register.** Where sources disagree, log the disagreement rather than silently picking a winner. Unresolved conflicts are findings, not noise.

### P4 — Adversarial Pass

**Mandatory. Non-negotiable. This is the phase that separates deep research from search.**

1. **Steelman the opposite.** Construct the strongest version of the conclusion you did not reach.
2. **Hunt disconfirmation.** Query specifically for evidence that your leading claim is false. If you have not run a query designed to break your own answer, P4 has not happened.
3. **Attack the weakest link.** Identify the single claim your conclusion most depends on and verify it independently at T1/T2.
4. **Check the null.** Would this evidence pattern look the same if the effect did not exist?

**Exit criterion:** Either the conclusion survived a real attack, or it changed. "I looked and found nothing contradictory" without a disconfirming query is a failed pass, not a passed one.

### P5 — Synthesis

Build the claim set, not a summary of what you read.

- One line per claim: **claim → supporting evidence → tier → confidence**.
- Claims are ordered by decision-relevance, not by the order you found them.
- Anything that survived P4 unchanged carries higher confidence than anything untested.
- What you could not determine gets its own section. Named gaps are deliverable; silent gaps are defects.

**Confidence calibration:**

| Level | Standard |
|---|---|
| High | Multiple independent T1/T2 sources, survived adversarial pass, current |
| Medium | Single T1/T2 or converging T3, no contradiction found, recency acceptable |
| Low | T3/T4 only, or unresolved conflict, or recency uncertain |
| Unknown | Named explicitly, with what would resolve it |

Never emit an ungraded claim. An ungraded claim inherits the reader's confidence, not yours.

### P6 — Output Contract

Fixed structure, so consumers can audit without re-reading the whole thing:

1. **Answer** — the decision-relevant conclusion, first, in one paragraph
2. **Claim set** — graded, per P5
3. **Conflict register** — unresolved disagreements between sources
4. **Gaps** — what remains unknown and what would close it
5. **Provenance** — source list with tier and access date
6. **Decay note** — which claims expire first and roughly when

---

## 4. Stop Conditions

Stop at whichever fires first:

- **Saturation** — new sources return already-captured claims and no new entities
- **Decision sufficiency** — the answer is now stable across the range of remaining uncertainty; more precision would not change the action
- **Budget exhaustion** — declare partial results with gaps named; do not silently continue
- **Blocking gap** — a required input is unobtainable; escalate rather than substitute inference

**Never stop on:** "I found something that sounds right." That is P1 exiting into P6.

---

## 5. Delegation Profile

Not all phases warrant the same execution cost. Match phase to executor.

| Phase | Delegate to autonomous loop? | Rationale |
|---|---|---|
| P0 Preconditions | No | Requires knowing the decision; cannot be inferred |
| P1 Landscape | Yes | Breadth-parallel, low judgment |
| P2 Acquisition | Yes | Mechanical fetch against a hierarchy |
| P3 Grading | Partial | Tiering is rule-based; incentive analysis is not |
| P4 Adversarial | No — supervise | Models converge on their own priors; self-attack is unreliable unsupervised |
| P5 Synthesis | Partial | Draft delegable, calibration is not |
| P6 Output | Yes | Formatting against a fixed contract |

**Cost discipline:** P1/P2 are the expensive phases in tokens and the cheap phases in judgment. If budget is constrained, cut breadth in P1 before cutting P4. A narrow-but-attacked conclusion beats a broad-but-unexamined one.

---

## 6. Anti-Patterns

| Anti-pattern | Tell | Correction |
|---|---|---|
| Search theater | High query count, single framing | Force divergent queries in P1 |
| Snippet synthesis | Conclusions drawn without fetching a full source | Mandatory fetch for any cited claim |
| Volume as rigor | Long output, no confidence grades | Enforce P5 grading |
| Confirmation loop | Every source agrees with the opening hypothesis | P4 disconfirming query is mandatory |
| Silent gap-filling | Inference presented in the same register as evidence | Gaps get their own section |
| Stale certainty | Present-tense claims about things that change | Recency status on every claim |
| Scope drift | Output answers a more interesting question than the one asked | Re-read Gate 0 before P6 |

---

## 7. Audit Trail

The method is only defensible if it is reconstructable. Retain:

- Gate 0 statement, verbatim, unedited after the fact
- Query log with phase attribution
- Source list with tier, access date, and fetch-vs-snippet status
- P4 record: what was attacked, what survived, what changed
- Deltas: any claim whose confidence moved, and why

An audit trail that was written after the conclusion is a rationalization, not a trail. Capture during, not after.

---

## 8. Known Limits of This Method

Stated so the method is not oversold:

- **It is expensive.** Full pipeline is inappropriate for most questions. Gate 0 exists partly to reject tasks that do not need it.
- **P4 is the hardest phase to enforce and the easiest to fake.** A disconfirming query that was designed to fail is worse than none, because it manufactures false confidence.
- **Source tiering is not source truth.** T1 primary sources have incentives too. Tier ranks proximity to origin, not honesty.
- **Saturation is detectable only within reachable sources.** It says nothing about what is paywalled, unindexed, or unpublished.
- **Confidence grades are subjective.** They are useful because they are explicit, not because they are accurate.
