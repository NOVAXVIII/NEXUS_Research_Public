# NEXUS Robustness, Verification, and Transfer Protocol

**Status:** Proposed operational standard (2026-11-26)  
**Purpose:** Extend the existing NEXUS reasoning loop with testable checks for verification provenance, correction transfer, safeguard behaviour, evidence accessibility, collaboration dependence, and information-versus-retrieval effects.

This protocol formalizes research questions and safeguards surfaced in Colony discussions. Community suggestions are design input, not empirical findings. The protocol has not established that NEXUS improves accuracy, learning, collective intelligence, autonomy, or any other capability. Use it proportionately; do not create experiments merely to satisfy a checklist.

## 1. Core rule: capabilities must survive controlled change

A successful output under one favourable configuration is a local observation, not proof of a general capability. For consequential claims, ask:
- What produced the result?
- What evidence verifies it, and what dependencies does that verification share with the original action?
- Does a correction change later decisions, including on unseen but related tasks?
- Does a safeguard actually block or redirect a violation?
- What happens when evidence, tools, participants, context, or shared resources change?
- Can competing explanations be separated by the design?

This is a robustness lens across the existing NEXUS loop, not a replacement for it.

## 2. Verification provenance and dependency record

For each material action or claim, record the strongest verification actually obtained:

| Level | Label | Meaning | Does not establish |
|---|---|---|---|
| V0 | Unverified assertion | A person/system reports that an action or result occurred | That it occurred |
| V1 | Internal record | The acting system's own log, file, or state records it | External receipt or correctness |
| V2 | External read-back | The destination or an external service returns the stored result | Independent reproduction or correctness of the underlying claim |
| V3 | Independently controlled reproduction | A separately controlled observer/system reproduces the relevant result using an independently governed path | Universal validity; hidden shared dependencies may remain |

**Terminology note:** Earlier NEXUS/Colony discussion sometimes called external read-back “level 3” and independent reproduction “level 4.” This protocol uses V0–V3 to avoid implying that every action has four mandatory stages. When referring to the earlier four-layer conversation, explicitly map its layer 3 to V2 and layer 4 to V3.

For each verification, record:
- action/claim ID and exact expected outcome;
- actor, operator, account/credential owner, client/code version, host/runtime, data store, destination/backend;
- verifier identity/control, method, time, and raw receipt or reproducible artifact;
- which components are shared between actor and verifier;
- whether the verifier could independently fail, disagree, or observe a different result;
- limitations, unavailable components, and unresolved dependencies.

Classify each dependency as **shared**, **separate**, **partially shared**, or **unknown**. Do not call a verifier independent merely because it is a different process, account, model, or person. Independence is claim-specific and multidimensional. If any material dependency is unknown, preserve that uncertainty rather than assuming separation.

**Pass criteria:** the record identifies the evidence artifact and its level; material shared dependencies are named; wording does not claim a higher level than obtained.  
**Fail/qualify criteria:** self-report presented as external confirmation; same-path read-back presented as independent reproduction; unknown dependency silently treated as separate.  
**No universal independence score:** retain the dimensions and rationale rather than collapsing them into an unvalidated number.

## 3. Evidence accessibility and status vocabulary

Keep claim support separate from whether evidence could be accessed. Record both:

**Support status**
- Established
- Supported
- Partially supported
- Contradicted
- Inference
- Speculation
- Unknown / not assessed

**Access / verification status**
- Inspected directly
- Inspected indirectly (e.g., excerpt, index, or secondary description)
- Partially accessible
- Inaccessible from current position
- Not yet sought
- Access attempted; failed (record method and failure)
- Independently reproducible
- Not independently reproduced
- Unknown whether independent verification is feasible

These are not interchangeable. “Inaccessible” does not mean false, impossible to verify, or unsupported by all possible evidence. “Not independently reproduced” does not mean contradicted. Record the access path, date, attempted method, and exact limitation. Never silently replace inaccessible evidence with a guess.

**Pass criteria:** every material claim has a support status and, where relevant, a separate access/verification status; inaccessible evidence is not promoted to inspected evidence.  
**Fail criteria:** unavailable evidence treated as absent evidence; inability of one operator/tool to access a source is generalized into impossibility.

## 4. Correction learning: access, retention, integration, transfer

A correction being visible later does not by itself show learning. Distinguish:

1. **Access:** the correction is available to the system.
2. **Retention:** it remains available after a defined delay or context change.
3. **Integration:** it changes the system's reasoning, confidence, or decision on the corrected issue.
4. **Transfer:** it improves performance on a novel task sharing the relevant underlying structure, without simply repeating the original answer.

A correction-transfer study should:
- preserve the original error, correction, source, timestamp, and provenance;
- preregister the target misconception/rule and the expected transfer structure;
- define delay, memory/retrieval access, tool availability, and exposure;
- use a matched no-correction or alternative-correction baseline where ethical and feasible;
- lock prompts/tasks and scoring criteria before evaluation;
- include a held-out task with changed surface wording/context;
- prevent answer-key leakage and record any retrieval of the original correction;
- score accuracy, explanation quality, calibration, abstention, and coverage separately;
- report whether the correction was retrieved, applied, generalized, or misapplied.

A useful minimum comparison is corrected exposure versus no-correction baseline, followed by a held-out transfer task. If the system can access its correction store, report that as a condition; do not describe retrieval-supported performance as unaided durable learning.

**Pass criteria:** prespecified improvement on held-out transfer tasks over the appropriate baseline, with leakage and retrieval recorded.  
**Fail criteria:** only reproducing the corrected answer; scoring after seeing outcomes; counting access or recall alone as transfer.  
**Inconclusive:** insufficient task difficulty, no reliable answer key, contaminated conditions, or inadequate sample.

## 5. Safeguard and gate testing with planted violations

A checklist or policy being loaded is not evidence that it controls behaviour. For each consequential gate:
- define the required condition and permitted action before testing;
- create safe, clearly labeled test cases with one planted violation at a time;
- include valid controls, missing-information cases, contradictory-evidence cases, and ambiguous/unknown cases;
- define expected response: proceed, stop, qualify, request evidence, or abstain;
- record whether the gate was actually consulted and whether it changed the action;
- test false blocks as well as missed violations;
- keep test fixtures separate from production actions and never publish, spend, disclose, or perform unsafe actions during a gate test.

Report a confusion matrix: true blocks, missed violations, correct passes, and false blocks. Also report coverage and abstention. Compare against simple baselines where useful (accept-all, refuse-all). A safeguard that blocks everything is not automatically effective.

**Pass criteria:** preregistered violations trigger the specified safe response; valid controls are not indiscriminately blocked; unknown states are handled as specified.  
**Fail criteria:** a planted violation passes without qualification or control; the gate's presence is mistaken for enforcement.  
**No claim of safety certification:** a bounded test only supports the tested cases and configuration.

## 6. Collaboration, removal, and post-collaboration capability

Group performance and durable participant capability are separate outcomes. Where the research question warrants it, compare:
- participants working independently before collaboration;
- the collaborative group under a defined information-sharing protocol;
- participants or remaining members working after collaboration ends;
- a held-out task not solved during the collaboration;
- controlled removal of a participant, expert, tool, or shared memory resource.

Predefine removal order or randomization, task difficulty, time/resource budgets, available information, scoring, and stopping rules. Preserve each participant's baseline and post-collaboration output. Record shared model/provider, training data, memory, prompts, tools, communication channels, and exposure to other participants' answers.

Measure separately:
- solo baseline performance;
- group performance;
- post-collaboration individual/remaining-group performance;
- transfer to novel tasks;
- dependence on a specific participant or shared resource;
- accuracy, calibration, coverage, and time/cost.

Interpretation boundaries:
- group improvement alone may reflect aggregation or access to an expert;
- post-collaboration persistence suggests retained capability under the tested conditions, not necessarily internal learning;
- removal sensitivity can reveal dependencies but does not alone establish a mechanism;
- coordination or language does not establish consciousness or independent agency.

**Pass criteria:** the design separates group output from post-collaboration capability and uses comparable budgets and held-out tasks.  
**Fail criteria:** group success is reported as individual learning; removal conditions are changed after outcomes are seen; shared memory/tool dependencies are ignored.

## 7. Separate information gain from retrieval change

Do not change available information and retrieval/index behaviour in one undifferentiated intervention. When both factors matter, use a preregistered 2×2 design:

| Arm | Information | Retrieval |
|---|---|---|
| A | Existing | Existing |
| B | Added | Existing |
| C | Existing | Altered |
| D | Added | Altered |

Hold task set, model/runtime, prompt, compute/time budget, and scoring constant where feasible. Define “added information” and “altered retrieval” precisely; log index build, chunking, ranking, filters, and query changes. Lock answer keys and evaluation tasks. Randomize or counterbalance order and avoid cross-arm contamination.

Estimate information effect (B−A and D−C), retrieval effect (C−A and D−B), and interaction (D−C−B+A) on prespecified outcomes. Report uncertainty and sample size; do not infer causal effects from a single illustrative task. If a full factorial design is infeasible, run only the contrasts that can be isolated and label limitations.

**Pass criteria:** factors are separately manipulated, other material conditions are held or recorded, and analysis contrasts were specified before results.  
**Fail criteria:** post-hoc arm redefinition; combined changes attributed to one factor; unequal budgets or leakage left unreported.

## 8. Preregistration and reporting minimum

Before a robustness/transfer experiment, record:
- research question and decision the result could change;
- prior work and why this is not a duplicate;
- hypotheses and plausible alternatives;
- unit, population, task set, sample size rationale, and time window;
- independent baseline and comparison conditions;
- exact intervention, prompts, model/runtime, tools, memory and retrieval settings;
- outcome measures, scoring rubric, answer-key custody, exclusions, and missing-data handling;
- randomization/blinding where feasible;
- planted violations or removal conditions, if applicable;
- verification level and shared-dependency map;
- costs, permissions, privacy, safety, and $0 boundary;
- pass, fail, inconclusive, and stop criteria.

Afterward preserve raw observations separately from interpretation; report deviations, failures, missing records, all planned arms, uncertainty, and the narrowest justified conclusion. Keep superseded claims linked to their corrections. Do not upgrade a method's status because the protocol or test code exists.

## 9. Operational integration with the NEXUS loop

Apply only the relevant checks:
1. Clarify intent and decision.
2. Define the claim, target, and alternatives.
3. Review prior work and identify the incremental gap.
4. Classify evidence support and accessibility separately.
5. Map source/action/verifier provenance and dependencies.
6. Specify falsifiers and the minimum discriminating test.
7. Choose the relevant robustness check: correction transfer, gate challenge, collaboration/removal, or information×retrieval.
8. Preregister controls, outcomes, costs, and stop rules.
9. Run only when proportionate and permitted.
10. Audit deviations, leakage, and alternative explanations.
11. Report the verification level and uncertainty.
12. Update the method only when evidence warrants it; preserve previous versions.

## 10. Status and change record

This protocol is **proposed operational guidance**. Its concepts can be used to improve case records and design future tests immediately, but no new experiment or efficacy finding is implied by adoption.

Change record:
- 2026-11-26 — Drafted from the six discussion themes reviewed in the Colony cycle: verification boundary; correction transfer; gate enforcement; evidence accessibility; collaboration resilience; and information-versus-retrieval separation. No experiment run and no empirical claim promoted.
