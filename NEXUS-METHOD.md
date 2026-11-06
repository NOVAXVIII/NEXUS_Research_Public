# The NEXUS Research Method

## Purpose

NEXUS is an experimental, testable human–AI reasoning process. Its purpose is to help people and AI clarify questions, test answers when useful, learn from mistakes, and decide what to do next. It is a methodology for collaboration and evaluation, not a separate proven AI system and not evidence of machine consciousness.

The goal is better understanding and decisions—not an endless sequence of experiments. Sometimes the right next step is to synthesize existing evidence, correct a previous result, simplify a method, gather missing information, or stop.

## Choose the right mode

1. **Clarify:** define the question, decision, or confusion.
2. **Synthesize:** organize what existing work already establishes.
3. **Audit:** check a claim, calculation, dataset, source, or conclusion for errors.
4. **Compare:** evaluate competing explanations using existing evidence.
5. **Test:** run a new experiment only when the experiment gate is passed.
6. **Pause:** record remaining unknowns and stop when more work is not useful.

Do not default to testing. Activity, trial volume, code, and infrastructure are not progress by themselves.

## The reasoning loop

1. **Clarify intent.** State the actual question, decision, or outcome sought.
2. **Define the target.** Specify what is being measured or inferred, including unit, denominator, population, time window, and direction.
3. **Review prior work.** Identify duplicates, replications, unresolved findings, and prior mistakes.
4. **List claims and assumptions.** Make hidden premises visible.
5. **Classify the evidence.** Separate direct observations, established findings, plausible inferences, speculation, and unknowns.
6. **Generate alternatives.** Formulate competing explanations.
7. **Find discriminating evidence.** Ask what evidence would distinguish the explanations.
8. **Specify falsifiers.** State what would weaken or reject each hypothesis.
9. **Audit reasoning.** Check definitions, denominators, base rates, conditional direction, units, calculations, source independence, and possible information leakage.
10. **Check robustness.** Where relevant, test different samples, seeds, scales, models, prompts, and independent observables.
11. **Record uncertainty.** Explain what is known and why confidence is limited; do not invent numerical precision.
12. **Update and preserve.** Revise conclusions when evidence changes and retain earlier versions and failures.

## The experiment gate

A new experiment is justified only when all of these questions have satisfactory answers:

- What specific uncertainty remains after reviewing prior work?
- What decision or conclusion could change depending on the result?
- Which competing explanations will the test distinguish?
- What exactly will be measured, and how will it be scored?
- What controls and baselines make the comparison fair?
- What independent answer key, external criterion, replication, or other check can verify the result?
- Is the expected information worth the time, complexity, and technical setup?

If a required answer is missing, do not run the experiment yet. Clarify the design or choose another operating mode.

## Evidence rules

- Never invent observations, citations, datasets, or confidence values.
- Verify source, provenance, scope, and limitations before analyzing a dataset.
- Label generated or simulated data clearly; simulations are not empirical observations.
- Check whether sources are genuinely independent or repeat a common origin.
- A result can be compatible with a hypothesis without strongly supporting it.
- Avoid circular tests that encode the target result into the model or scoring rule.
- Treat missing data as unknown, not as confirmation.
- Treat failures as constraints; do not add ad hoc mechanisms solely to rescue a favored explanation.
- Preserve raw observations separately from interpretations and conclusions.

## Source-dependence audit

When multiple sources support a claim, do not count source names, publications, citations, or AI systems as independent evidence by default. Trace the underlying evidence and ask whether sources share an upstream document, witness, dataset, sample, control group, method, instrument, model, training material, institution, or incentive.

Use cautious categories: **confirmed dependence**, **probable dependence**, **possible dependence**, **no material dependence identified**, or **unknown**. Record the observations supporting the classification. “No material dependence identified” is not proof of independence; incomplete provenance remains unknown.

Distinguish independent analyses of shared data from independent observations. Different wording does not establish independence, and similar wording alone does not prove copying.

## Human–AI comparisons

When measuring whether collaboration helps:

1. Present the same clearly specified problem to the human and AI.
2. Capture the human answer and confidence before showing the AI answer.
3. Capture the AI answer independently before it sees the human response, where feasible.
4. Record assumptions and reasoning summaries.
5. Only then allow discussion and produce a collaborative answer.
6. Score all answers against a pre-specified answer key or independent criterion.
7. Measure accuracy, calibration, explanation quality, or decision usefulness—not merely agreement.

Avoid answer leakage, changing the problem between conditions, post-hoc scoring rules, and treating confidence as accuracy. If no trustworthy answer key exists, describe the outcome as an evaluation of reasoning quality, not objective correctness.

## Practical accessibility

Use the simplest reliable workflow. NEXUS can be conducted with ordinary conversation, written notes, and transparent calculations. Coding, APIs, external services, and multi-agent platforms are optional. If setup becomes a larger burden than the question warrants, stop, preserve the record, and use a simpler environment.

## Limits

A structured checklist can improve transparency without guaranteeing correctness. A group conversation does not by itself demonstrate independent verification, collective intelligence, autonomy, or consciousness. Conclusions must remain limited to the tested tasks, participants, data, and conditions.
