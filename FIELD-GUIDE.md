# Run a first cycle

[Home](README.md) · [Cycle note](templates/CYCLE-NOTE.md)

Use an existing issue or project record. Pick a real workflow with an available owner and a plausible comparison. Start manually if that answers the question sooner. Do not build a framework tool before the practice itself proves useful.

## Before starting

- Find existing work and its owner. Identify the user outcome and the main uncertainty.
- Choose a baseline: the current manual method, current agent workflow, or another appropriate alternative. Record why it is comparable.
- State the hypothesis, target population or task set, outcome definition, observation window, resource budget and quality floor before seeing results. Thresholds belong to the actual case; this framework supplies no universal conversion target.
- State scope, authority, privacy constraints and stop conditions. For agent work, name the model/tool/configuration and artifact version when relevant, without recording secrets.
- Decide only what the next safe test requires. Give other material open choices an owner and trigger.

## Evidence and measures

Choose a primary outcome and a small set of guardrails. Always state the denominator, period and inclusion rules. Keep failures, withdrawals, retries and excluded cases visible.

- **User value:** completed intended outcomes / eligible attempts; time to first useful outcome; repeat use in a defined cohort; actual willingness to pay when ethically and appropriately tested. Registrations and generated outputs alone do not show value.
- **Quality:** acceptable outcomes / all assigned tasks; failure severity; correction and reopening rate; regression or unauthorized-action incidents. Define “acceptable” before judging. Report small samples as counts, with uncertainty, rather than broad claims.
- **Learning speed:** elapsed time from framing the question to an evidence-backed decision, including queues and review. PR count, token count and agent count are diagnostic activity measures, not learning outcomes.
- **Economics:** full experiment cost / accepted outcomes, with human time reported separately or valued at a stated rate. Include unsuccessful attempts, tools, compute, review, rework and integration. Separate one-time experiment costs from ongoing operation and maintenance costs over a stated period. If no outcome is accepted, report the costs and zero accepted outcomes rather than a misleading ratio.
- **Coordination:** avoidable duplicate effort, review queue age, handoff failures and integration rework. Interpret these alongside outcomes; eliminating all parallel exploration can also slow learning.

For a model or workflow comparison, use the same representative task set, acceptance criteria and resource constraints where possible. Separate development examples from held-out evaluation cases; rerun stochastic cases when warranted and report variation. Randomize or counterbalance order when learning effects matter. Do not train to the test or let the author silently change the rubric after seeing results. Record unavoidable differences and avoid attributing every change to the framework.

## At the review point

Compare the result with the baseline and guardrails. Inspect disconfirming cases and missing data. Decide whether the evidence supports continuing, changing the hypothesis, stopping or running a narrower follow-up. Name who owns the decision and follow-up. If a safety boundary is crossed, stop the affected activity and handle it through the applicable process; aggregate gains do not cancel the incident.

For a pilot, a local improvement is a reason for another bounded test, not proof of general superiority. Broader claims require replication across relevant tasks, people and conditions, with the limits visible.

## Worked example: reducing review burden

**Illustration only. All tasks, numbers and results below are hypothetical.**

A maintainer spends too much time checking small documentation changes. The question is whether one bounded authoring agent plus a separate evidence check improves accepted outcomes at the same quality floor compared with the current workflow. Adding more authors is not assumed to help.

Use comparable sets of ten small changes. Freeze the rubric: factual accuracy against sources, working links, correct scope and no sensitive disclosure. Record elapsed time, agent/tool cost, reviewer minutes, failed attempts and corrections. A human maintainer retains acceptance authority. Defer automation of publication until evidence shows it is useful and it is separately authorized.

Suppose the baseline yields 9/10 accepted changes in 90 reviewer minutes; the candidate yields 8/10 in 50 minutes, with a repeated sourcing defect. The candidate is faster to review but has not met a predeclared 9/10 acceptance floor. Investigate the defect and retest within the approved budget rather than report a productivity win. Neither sample establishes business value or a universal framework advantage.

Record this as an illustrative design until a real, permissioned run supplies evidence. Do not enter hypothetical results into the practice inventory as observations.
