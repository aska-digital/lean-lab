# Sovereign Neo-Lab: Methodology and Operating Manual

[Home](README.md) · [Manifesto](MANIFESTO.md) · [Framework](FRAMEWORK.md)

Status: working methodology for review. Sections marked MEASURE state hypotheses that must be established against a baseline before being reported as results.

## Part I. Virtual-Human Swarm Architecture

The swarm is a set of bounded agent personas. Each persona has one responsibility, a defined set of permissions, and a defined output contract. Role separation is the main control: no persona both produces and approves its own output.

### 1. Personas

Architect. Owns the specification: the outcome, interfaces, invariants, and decomposition into components. Produces the design record. Does not write production code for components it will later review.

Kernel engineer. Implements against the specification in the target language and runtime. Produces code, build files, and tests. Has write access only to its assigned component and branch. Cannot merge.

Adversarial auditor. Attempts to falsify the implementation. Reads the specification, constructs failure cases, looks for trust-boundary violations, unsafe defaults, undefined behavior and specification drift. Its job is to find what the kernel engineer missed. It has read access to the artifact and the spec, and no authority to modify the implementation except by filing findings.

Formal mathematician. States and checks the properties that admit formal treatment: invariants, bounds, termination, equivalence between a reference model and an optimized implementation. Produces machine-checkable proofs or explicitly reports which properties it could not formalize.

Integration owner (human). Holds merge authority, resolves disagreements between personas, and records decisions. This role is never delegated to an agent.

The persona names used in our working notes map onto these roles. A role is a function, not a fixed identity. One agent may hold several roles across different tasks, but never the producer and approver roles for the same artifact.

### 2. Handoffs

Every handoff carries: the source request and its scope, the specification version, the artifact version (commit hash), unresolved risks, checks performed and their results, and the next owner. A handoff without an artifact hash is invalid, because verification refers to a specific version.

### 3. Landlock pre-execution sandboxing

Agents that execute code do so under a Landlock sandbox applied before the process runs. Landlock is a Linux security module available to unprivileged processes since kernel 5.13. It restricts filesystem access by a ruleset the process installs on itself, and the restrictions are inherited by children and cannot be lifted by the process.

Rules:

Apply the ruleset before any untrusted code executes, not after. The verification step must confirm the restriction is active by attempting a forbidden access and requiring it to fail.

Grant read access only to the specification, the artifact under review, and required toolchains. Grant write access only to the component's build output directory. Network egress is controlled by a separate layer; Landlock is one control, not the whole sandbox.

A check that the sandbox is not in effect is a hard failure, not a warning.

### 4. Zero-trust cryptographic gates

No artifact moves between stages on the producer's word. Each gate verifies:

Identity: the commit is signed by a key authorized for the stage that produced it.

Integrity: the artifact hash matches the hash recorded in the handoff.

Policy: the artifact passed the checks the stage requires, and the check results are bound to that hash.

Authorization: a human approval, where required, references the same hash.

Gates fail closed. Missing evidence is a failure. Evidence is bound to content, so a passing result for version A cannot be reused for version B. Any change after review invalidates the review.

### 5. Deterministic commit pipeline

The pipeline runs from a pinned toolchain in a hermetic environment, with a fixed input set and no ambient state. The same source at the same commit must produce bit-identical build outputs, or the difference must be explained and recorded.

Stages: specify (spec file validated against schema), build (pinned toolchain, recorded environment), test (deterministic seed, recorded results), audit (adversarial findings filed), prove (formal checks where applicable), gate (cryptographic checks), merge (human authority).

Non-determinism is treated as a defect. Random seeds are fixed and logged. Timestamps and host paths are excluded from artifacts.

## Part II. Verification standard

A claim is accepted only with evidence at the level it asserts.

Level 0, observed: a behavior was seen once. Not evidence of reliability.

Level 1, tested: a reproducible test passes at a recorded commit, with stated coverage.

Level 2, audited: an independent persona attempted to falsify the claim and the attempts and outcomes are recorded.

Level 3, proven: a machine-checked proof covers the stated property under stated assumptions.

Reports separate passed, failed, blocked and untested areas. A test pass is never described as proof of a property it did not check.

## Part III. Mathematical determinism over statistical heuristics

Where a property can be expressed as an invariant, state it and check it: conservation of a quantity, bounds on an index, equivalence of two implementations on a defined domain, termination of a loop with a decreasing measure. Prefer the checkable form. If an invariant cannot be stated, say so and mark the claim as heuristic, with the sample size, distribution assumptions and failure rate reported.

Statistical methods remain appropriate for estimating quantities with real uncertainty, such as performance under load or user behavior. They are not a substitute for correctness properties.

## Part IV. Silicon economics

The cost of an artifact is not its token count. Track the full path.

Hardware multiplier: how much useful output one unit of hardware produces over its service life, measured as completed verified work per unit time at a stated utilization. Report the utilization. A high multiplier at low utilization is not an economic result.

TCO efficiency: total cost of ownership per verified outcome, including hardware depreciation, power, cooling, operator time, agent and API spend, retries, human review time and maintenance. Report per outcome, with the outcome definition stated.

Memory bandwidth wall: for memory-bound workloads, throughput is limited by data movement rather than arithmetic. Measure achieved bandwidth against the hardware's peak, identify the limiting access pattern, and optimize data layout and reuse before adding compute. Report arithmetic intensity and the roofline position of each workload.

Measurement rules: state the baseline, the workload, the input set, the hardware and software versions, and the measurement method. Repeat measurements and report variance. A figure without these is a claim, not a result.

## Part V. Sovereign Neo-Lab operating manual

This part describes how one researcher coordinates many parallel research efforts. The model depends on the discipline above. Without specification, verification and gates, parallelism multiplies errors faster than it multiplies results.

### 1. Structure

Each research organization has one accountable owner, one canonical repository, one integration branch, and a written scope. Work across organizations is coordinated by a shared index that records owner, status, and open decisions. Duplicate implementation across organizations is avoided by checking the index before starting work.

### 2. Daily cycle

Orient: review the index, open decisions and failed gates from the previous cycle.

Frame: choose the decision-relevant uncertainty for each active organization. Write the specification and acceptance criteria before any generation.

Run: dispatch bounded persona tasks under the swarm architecture. Keep the number of concurrently open artifacts within review capacity. Stop spawning work when review and integration queues grow.

Verify: run the gates. Record evidence level per claim.

Decide: continue, change, stop, or name the missing evidence. Record each decision with its trigger for revisiting.

Retain: write the negative results, the decision log, and any reusable procedure or test.

### 3. Work-in-progress limit

The limiting resource is human review and decision time, not agent throughput. Set the limit on open artifacts awaiting integration to what one integration owner can review at the required standard. Measure review backlog and time-to-decision weekly.

### 4. Scaling across domains

Each domain carries its own specification language, verification tools and risk level. High-assurance domains require Level 2 or Level 3 evidence before integration. Exploratory domains may integrate at Level 1 with an explicit label. The level required is set in the specification, not chosen after the fact.

### 5. Protecting the operator

A single operator working at night is a reliability and safety risk. Consequential actions are not taken unattended unless the gate and authority rules for them have been defined in advance. Scheduled agent runs do not widen permissions. Access to data and external systems is granted per task and revoked when the task closes.

### 6. Intellectual property and records

Every artifact is tied to a specification version, a commit, and the decision that authorized it. This record is the basis for provenance claims. Third-party material is recorded with its source and license, following SOURCES.md.

## Part VI. Measurements to establish before claiming results

M1. Review and rework rate per artifact, compared against a stated pre-swarm or single-agent baseline.

M2. Fraction of defects found by the adversarial auditor that the kernel engineer's own tests did not catch.

M3. Gate failure rate and the causes of gate failures.

M4. Bit-reproducibility rate of the build pipeline across repeated runs.

M5. Hardware utilization and verified outcomes per unit time.

M6. TCO per verified outcome, with the outcome definition and cost components listed.

M7. Achieved memory bandwidth against peak for each memory-bound workload.

Until these are measured, the methodology is a hypothesis with a defined test, and should be described that way.

## Part VII. Open questions

Which properties in our highest-risk domains can be stated formally at reasonable cost.

Whether independent adversarial review by a model reliably catches defects a human reviewer would catch, and under which conditions it fails.

How much of the Landlock ruleset can be generated from the specification without weakening it.

Whether the efficiency gains hold once the review and integration queue is included in the cost.

## Part VIII. Falsification, novelty tiers and retraction

This part governs how a claim earns a name. It applies to every organization in the Neo-Lab.

### 1. Pre-registration

Before a test is run, record the hypothesis, the exact domain (for example exact rational or integer arithmetic over Q or Z where the domain allows), the adversarial null, the normalization that removes trivial explanations, the falsification criterion, and the evidence level required. The record is committed before the result is generated. A criterion changed after the run is a new hypothesis, not a revision of the old one.

### 2. Adversarial nulls and null-normalization

Every candidate is compared against a null that a reasonable skeptic would propose. A result counts only if it exceeds the null under the stated normalization. Where a candidate collapses under its null, the collapse is the result.

### 3. Verification route

Where the property admits a formal statement, it is checked in a proof assistant. Where it does not, it is checked by reproducible computation with fixed seeds and recorded environments, and the claim is held at Level 1 or Level 2 accordingly. Formal checks must be run by the formal mathematician persona, and the producer may not sign its own proof.

### 4. Novelty tiers

N0, prior art. Known results are quarantined and cited with their sources. They are not presented as contributions, and their presence in a candidate is reported.

N1, incremental advance. A scoped extension of known results. The write-up states the exact reach of the extension, including the cases it does not cover.

N2, canonical declaration, called "The Theorem" in working notes. Reserved for results that have complete machine-checked formalization with zero sorry, zero axiom and zero cheat. No document, title, site copy or conversation may use N2 language before that condition is met and recorded.

A result is assigned the tier its evidence supports, and no higher. Tier changes are recorded in the decision log.

### 5. Retraction

When a hypothesis collapses, record the collapse in the same location as confirmed results, with the null that survived, the counterexample, and the date. Publish retractions on the same surface as the original claim. A retraction is a completed cycle, not an incident.

### 6. Naming

Names describe what was shown. Do not give a result a legendary name, and do not use a historical figure's name for a result, before the N2 condition is met. Placeholder labels must be marked as placeholders.

### 7. Lineage

The Ramanujan, Hawking and Bayt al-Hikma traditions are honored by applying their standards, not by quoting or mythologizing them. Tribute means that a classical intuition is tested with exact arithmetic and adversarial nulls. It does not mean reverence, folklore, or a memorial that is not backed by a check.

## Part IX. Measurements to establish before claiming results (falsification)

F1. Number of pre-registered hypotheses, and the number confirmed, falsified and inconclusive. Report all three.

F2. Number of retractions published, with the cycle in which each was found.

F3. Count of claims by novelty tier, and any claim presented above its tier.

F4. Count of formal artifacts with sorry, axiom or cheat remaining. Must be zero for any N2 claim.
