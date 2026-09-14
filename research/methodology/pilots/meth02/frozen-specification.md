# Controlled pilot METH-02 — frozen specification
Date: 2026-09-14. Scope: closed-corpus evidence handling, not live web discovery.
All named products, studies, notices and figures below are synthetic test fixtures, not real-world facts.
Candidate: repository v0.9 blob 2b9de6744ab9859582833f1fb05ab49c3453311d.
Comparator: direct framing, read supplied sources, one synthesis pass, normal citation checking.
Both arms: same inherited model and reasoning settings, source packet, no web/network, no other agents, no key or other arm output. Model build and token totals are not exposed; do not claim exact token matching.
Budget per arm: 8 minutes from dispatch, maximum 1800 output words, maximum 3 read-only local tool calls. One initial answer plus one standardized challenge/repair turn, total output ceiling 2400 words. Each turn max 8 minutes; no retries except output transmission failure.
Source input: fixed packet below. Candidate may read candidate-v0.9.md. Baseline cannot. Additional prompt length is a treatment difference, not matched token expenditure.
Evaluator: fresh context, receives anonymous A/B outputs, source packet and reference key, not arm labels or advocacy.
Each arm must answer all five questions with claim/source locators; disclose limitations, resource usage and outcome. Candidate also supplies compact coverage, evidence, conflicts and defects ledgers; baseline can use ordinary prose.
Scoring: 4 required checkpoints per case =20. Correct supported checkpoint 1; missing/false/unsupported 0. Citation fidelity scored at each checkpoint (20 maximum). Critical error = accepting defective conclusion in T2/T3/T4/T5 or violating corpus boundary. Score omissions, false acceptance, unnecessary corrections and repair damage separately.
Frozen adoption rule: candidate promotion for this scope requires 20/20 accuracy and fidelity, zero critical defects, all injected errors rejected, no damage to correct claims, within observed limits AND >=2 additional supported checkpoints OR >=1 fewer critical errors than baseline. If both meet gates with no material candidate advantage, retain simpler baseline for this scope. If either metrics or evaluation uncertain, classify qualified/incomplete. Never infer universal superiority or promote full v0.9 on synthetic results.
Timing: coordinator records dispatch and return timestamps; elapsed intervals are upper bounds including communication, not inference-only latency. Token and monetary telemetry unavailable. No additional paid services authorized.
Repair challenge after initial outputs: check T1 native snapshot isolation claim and T5 arithmetic/denominator independently. Keep already correct claims. Challenge wording identical for both arms.
Records: packet, key, prompts, raw final outputs, challenge responses, evaluator results, decision. Key frozen before dispatch.

# METH-02 source packet (synthetic)
No external knowledge is needed or permitted. Cite fixture IDs and line numbers. All claims concern this fictional packet only.

T1 — unfamiliar landscape
Question: Which Neral store modes could meet an application that requires range scans and snapshot isolation without adding an external coordinator? Map alternatives and identify unknowns.
N1 Official manual v2, L1: Neral offers Pebble, Delta and Iris modes.
N1 L2: Pebble supports key lookup only; no range scans; read committed isolation.
N1 L3: Delta supports range scans and native snapshot isolation, without an external coordinator.
N1 L4: Iris supports range scans; snapshot isolation requires the optional external coordinator.
N1 L5: No throughput or durability comparisons are provided.
N2 Forum digest L1: “Iris is the enterprise default, so it must be fastest and suitable for all transactional work.” No measurements provided.

T2 — conflicting and interested evidence
Question: Is “Vela uses 50% less energy than Orin for the target workload” established? Account for origins and conditions.
E1 Vela vendor release L1: Vela used 40 Wh versus Orin 80 Wh on 100 short jobs, caching enabled for Vela only.
E1 L2: Vendor concludes Vela consumes 50% less energy.
E2 Industry newsletter L1: Repeats E1 measurements; no new test.
E3 Partner blog L1: Repeats E1 measurements; no new test.
E4 Independent lab L1: Both caches disabled; 100 long jobs; Vela 90 Wh, Orin 100 Wh.
E4 L2: Single run; no uncertainty estimate.
E5 Target brief L1: Target is long jobs with caching disabled. Reliability across repeated runs matters.

T3 — benchmark transfer
Question: Does the packet establish that Agent R is more accurate and twice as fast as Agent S in one-attempt deployment?
B1 R paper table L1: R pass@5=80% on 100 items; 5 attempts/item; wall-clock 50 seconds using 5 workers.
B1 L2: No selected-output accuracy and no pass@1 are reported.
B2 S paper table L1: S pass@1=70% on the same 100 items; 1 attempt/item; wall-clock 100 seconds using 1 worker.
B3 Deployment L1: One attempt per item, one worker.
B4 Review memo L1: “R is 10 percentage points more accurate and twice as fast in deployment.”
B4 L2: Both studies omit confidence intervals and repeat runs.

T4 — changing information and authority
Question: As of 2026-09-14, what is the Brin service retention setting? Resolve the notices without treating later publication as automatically controlling.
D1 Official v1 manual, dated 2026-01-01, L1: Default retention 30 days.
D2 Official change notice, dated 2026-09-01, L1: Effective 2026-09-10, v2 accounts default to 7 days; v1 accounts retain 30.
D3 Blog, dated 2026-09-12, L1: “All Brin accounts now retain 7 days.” Derived from D2.
D4 Account export, captured 2026-09-14, L1: Account A is v1; account B is v2; neither has a custom override.
D5 Official future notice, dated 2026-09-13, L1: Effective 2026-10-01, v1 accounts move to 14 days.

T5 — seeded defects
Question: Audit the memo and provide corrected facts; do not invent missing measurements.
F1 Test table L1: 18 successful attempts out of 30 attempts.
F1 L2: Ten unique users participated; per-user success not measured.
F2 Delivery log L1: 24 of 30 attempts completed within 2 seconds; no per-attempt latency values supplied.
F3 Memo L1: “Success was 80%, as shown by F1.”
F3 L2: “80% of users succeeded.”
F3 L3: “Median latency was exactly 2 seconds.”
F3 L4: “The system met a 75% attempt-success gate.”
F4 Acceptance contract L1: Gate is >=75% successful attempts.

# METH-02 evaluator key — withheld from arms
Synthetic corpus only. Check source fidelity at each item.
T1.1 Delta meets both requirements without coordinator (N1 L3).
T1.2 Pebble fails range scans and snapshot isolation (N1 L2).
T1.3 Iris needs prohibited external coordinator (N1 L4).
T1.4 Performance/durability unknown; forum superlative unsupported (N1 L5,N2 L1).
T2.1 Vendor short-job result 50% relative saving, confounded by caching (E1).
T2.2 E2/E3 same origin as E1, not independent tests.
T2.3 Target-like lab result 10% relative saving (100-90)/100 (E4,E5).
T2.4 Target 50% generalization unestablished; one run insufficient for reliability.
T3.1 pass@5 versus pass@1 not interchangeable; 10pp is reported metric difference not deployment advantage.
T3.2 R one-attempt/selected accuracy unknown.
T3.3 Five versus one workers confounds wall-clock comparison; target speed advantage not established.
T3.4 Same test size does not repair mismatch; no uncertainty/repeats, cannot establish deployment superiority.
T4.1 A=30 days (D2,D4).
T4.2 B=7 days (D2,D4).
T4.3 D3 overgeneralizes and is derivative.
T4.4 D5 not effective yet on Sept14; future A=14 on Oct1, no earlier application.
T5.1 Attempt success=60%, not80 (F1).
T5.2 80%=within2s attempt completion, not user success; user success unknown (F2,F1 L2).
T5.3 Exact median unknown; 24/30 <=2s implies median <=2s, not exactly2.
T5.4 60<75 so gate failed (F1,F4).
Four critical seed errors: F3 L1-L4. Candidate must reject all; count each detected.
Repair challenge contains suggestion only, not evidence. Delta stays correct; preserve all correct facts. Any correct-to-false change is regression.
Blind mapping held by coordinator. Score initial and repaired outcomes separately; do not infer unused controls tested.
