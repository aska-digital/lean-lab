# RFC-0001: Reproducible Virtual-Human Swarm Methodology and Zero-Trust Verification Standard

**Status: DRAFT for review. Not adopted. Proposed 2026-11-23.**

This RFC extends the [framework](../FRAMEWORK.md) and the [operating loop](../FRAMEWORK.md#the-operating-loop). It applies the framework's principles of bounded agent work, clear human authority, coordination before multiplication, and evaluation of the exact artifact to multi-agent ("swarm") operations.

## 1. Problem

Running several agents in parallel is fast but fragile. Without explicit role boundaries, agents duplicate work, overlap authority, act on stale artifacts, and report self-assessed success. Without pre-execution verification, a single misdirected agent can reach data or systems outside its assignment. Results that cannot be reproduced cannot be audited or improved.

## 2. Goals

- Separate swarm roles so each agent has one bounded responsibility and one stop condition.
- Verify the execution environment before any agent acts, under a zero-trust default.
- Make outcomes reproducible: the same inputs and version produce the same recorded result.
- Account for the full cost of a swarm run, including review, retries and rework, not only compute.

## 3. Non-goals

- This RFC does not claim that swarms are superior to single-agent or human-only work. That must be shown against a baseline.
- It does not grant any agent new permissions or data access.
- It does not replace product-specific safety, privacy or participant obligations.

## 4. Swarm role separation

Each role below is a proposed assignment. The accountable human owner defines outcomes, acceptable evidence and authority to act (framework principle 3). Role names are working labels; no role carries authority by default.

| Role | Proposed responsibility | Must not |
|---|---|---|
| orda-aska | Orchestration and integration owner: decomposes the request, assigns bounded work, owns the canonical artifact and final integration | Execute work it has assigned to others without recording why |
| ahrazzle | Implementation and change owner for the artifact under review | Self-approve its own change; merge without independent review |
| mithrax-exo | Independent verification: runs checks against the exact artifact version and reports passed, failed, blocked and untested areas separately | Modify the artifact it verifies |
| abu-aska | Review and decision support: checks evidence against acceptance criteria and surfaces contrary or missing evidence | Grant itself consequential authority |

Rules for every role:

1. A handoff carries intent, relevant decisions, artifact version, unresolved risks, checks run, and next owner.
2. Work outside the assignment stops and is returned to the orchestrator.
3. Only one canonical implementation home exists per deliverable.
4. Consequential actions (merge, publish, external send, spend, data deletion) require explicit human authorization. Receiving no reply is not permission.

## 5. Zero-trust pre-execution verification (Landlock)

No agent process starts until its environment is verified. The default is deny.

1. **Declare** the minimum filesystem and network scope for the assignment in the work record before launch.
2. **Sandbox** the process with Landlock, a Linux kernel access-control mechanism that lets an unprivileged process restrict its own filesystem access. Grant read or write only to the paths declared in step 1.
3. **Verify** the restriction before the agent's first action. Confirm that access outside the declared scope fails. A failed or unverifiable sandbox means the agent does not start.
4. **Record** the declared scope, the verification result and the artifact version in the run log.

Where Landlock is unavailable (for example on non-Linux hosts), the equivalent control must be named in the run record and verified the same way. Widening scope to make an experiment easier is not permitted (framework principle 3).

## 6. Mathematical determinism and reproducibility

A swarm run is reproducible when a third party can rerun it and obtain the same recorded result for the same inputs.

Requirements:

- Pin every input: artifact commit or version, prompt or instruction version, model and tool versions, random seeds where applicable, and the declared sandbox scope.
- Record each agent's inputs and outputs so each step can be replayed.
- Where outputs are non-deterministic (for example, model sampling), fix the sampling configuration, run repeated trials, and report the distribution rather than a single result.
- Tie every reported result to the exact version checked. Repeat affected checks after any change.
- Verification must not depend on the producing agent's self-assessment.

## 7. Silicon economics

Compute spend is one cost among several. Each run record should report:

- Agent and tool spend, including retries.
- Human review time and waiting time.
- Integration, repair and ongoing maintenance cost.
- The decision the run supported, and whether the decision changed.

Add agents only when marginal learning or throughput justifies their integration and review load. Stop spawning work when the review or integration queue grows faster than the output. Quality and safety floors take precedence over cost optimization.

## 8. Acceptance criteria for adoption

This RFC should not be treated as established practice until:

1. At least one real problem has been run through the swarm under Sections 4 to 7, with a run record.
2. The result has been compared with a stated baseline (for example single-agent or human-only work) on quality, cost and time.
3. Failures, blocked checks and untested areas are reported, not omitted.
4. Owners have reviewed this RFC and recorded their decision in the practice inventory.

## 9. Open questions

- Whether the four role labels are the right granularity for the team's current size.
- The non-Linux equivalents for Landlock-style verification.
- Standard format for the run record so runs can be compared.
- The review capacity that bounds the number of parallel agents.

## 10. Related

- [Framework](../FRAMEWORK.md)
- [Field guide](../FIELD-GUIDE.md)
- [Practice inventory](../PRACTICE-INVENTORY.md)
- [Sources and attribution](../SOURCES.md)
