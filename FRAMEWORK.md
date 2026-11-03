# Framework

[Home](README.md) · [Field guide](FIELD-GUIDE.md) · [Practice inventory](PRACTICE-INVENTORY.md)

## The objective

Learn which problems are worth solving and deliver outcomes people can use, with sustainable economics and responsible control. Improve the time and total cost needed to reach a justified decision at an acceptable quality level. A faster loop that tests the wrong thing or conceals its failures is not an improvement.

Keep three questions separate:

- **Value:** does this solve a real problem for the intended people, and is there evidence of continued use or a viable business?
- **Capability:** does the system work reliably in the conditions that matter?
- **Operation:** can people and agents deliver, review, maintain and change it at an acceptable cost and risk?

A passing software test supports capability within its coverage. It cannot establish customer demand. A promising interview cannot establish reliability or unit economics.

## Principles and mechanisms

### 1. Work from reality

Start with an actual goal, workflow and constraint. Identify the assumption whose failure would most change the next step. Distinguish an observation, an interpretation and a hypothesis. Agents can organize evidence and generate alternatives; synthetic personas and repeated model agreement do not substitute for independent evidence from the people concerned.

**Mechanism:** state a falsifiable question and the observable behavior that would change the decision. Record contrary and missing evidence alongside supporting evidence.

### 2. Preserve options until context makes a choice useful

Keep purpose clear while leaving implementation choices open. Use a reversible default when it permits useful progress. Name a trigger, an owner and, where needed, the latest safe decision point. Reassess before dependencies make a temporary choice expensive to replace.

**Mechanism:** a few lines in the existing issue: open choice; current evidence; temporary default and reversal; trigger; owner and decision authority. Decide earlier for lead times, external commitments, irreversible actions and protection from harm. Waiting is valuable only while useful learning outweighs delay and preserves options. See the pending [Compass proposal](https://github.com/Moissanite-Labs/compass/pull/12), which this framework generalizes without replacing.

### 3. Give agents bounded work and people clear authority

The accountable owner defines the outcome, acceptable evidence, constraints, resources and who can authorize consequential actions. An agent's assignment states what it may do, where it must stop and what it must return. Responsibility does not disappear when work is delegated.

**Mechanism:** link the source request and current scope to the deliverable. A handoff carries intent, relevant decisions, artifact version, unresolved risks, checks and next owner. Learning preferences, encountering a useful opportunity or receiving no reply does not create permission. Use only appropriately authorized data and actions. Do not widen access to make an experiment easier.

### 4. Make the smallest useful test

Choose the least costly credible way to answer the question: observation, a manual service, a prototype, a narrow production slice or a controlled comparison. Scope depends on the uncertainty and possible harm. Include enough of the real workflow to avoid optimizing an isolated step that fails in context.

**Mechanism:** define acceptance and stop conditions before execution. Protect privacy, consent, safety, accessibility and applicable obligations from the start. A minimal product does not justify minimal protection.

### 5. Coordinate before multiplying work

Find existing issues, branches, experiments and owners before creating another implementation. Parallelize independent questions or distinct components when that shortens the critical path without overwhelming review. Deliberately duplicated evaluation can be useful; accidental duplicate implementation is waste.

**Mechanism:** one canonical implementation home and an accountable integration owner. Set a work-in-progress limit based on review capacity, explicit handoff boundaries and a shared output contract. Stop spawning work when marginal learning is low or integration and review queues grow. Record whether a result is proposed, tested, reviewed, merged, integrated or in use; these are different states.

### 6. Evaluate the result, including the cost of checking it

Judge the delivered artifact against the actual task, failure cases and operating constraints. Use independent review where required; agent self-assessment is a useful input, not independent validation. Tie evidence to the version checked and repeat affected checks after changes.

**Mechanism:** report passed, failed, blocked and untested areas separately. Include human review time, agent/tool spend, retries, waiting, integration, repair and ongoing maintenance. Local correctness does not prove downstream integration or live behavior. Quality and safety floors constrain speed and cost optimization.

### 7. Change course and retain what was learned

End a cycle with a decision: continue the current hypothesis, change it, stop, or gather a specific missing piece of evidence. An inconclusive result is a valid result. Choose what would resolve it rather than quietly counting it as success.

**Mechanism:** preserve the result, limitations, decision and revisit trigger with the work. Turn recurring, well-understood lessons into a test, reusable procedure, interface or tool when expected reuse justifies its upkeep. Record negative results so another agent does not repeat the same failed search.

## The operating loop

1. **Orient:** locate the actual need, existing work, owner and authority; separate knowns from assumptions.
2. **Frame:** choose the most decision-relevant uncertainty, baseline, measure and guardrails.
3. **Test:** run a bounded experiment or deliver a useful slice, with explicit scope and stop conditions.
4. **Verify:** inspect behavior and source evidence, including failure cases, review and full cost.
5. **Decide:** continue, change direction, stop or resolve a named uncertainty; defer unrelated choices with triggers.
6. **Retain:** update the work record and reusable knowledge, then choose the next relevant question.

This is an adaptation of Build–Measure–Learn, not a new mandatory six-stage approval process. Steps can overlap. Routine reversible work needs little ceremony; consequential uncertainty deserves a stronger record. Optimize the whole path to a useful decision, not the number of completed loops.
