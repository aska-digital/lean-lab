# Lean Lab

Lean Lab is the Neo-Lab doctrine for small teams and solo operators who build with agents. It extends Eric Ries's Lean Startup loop of Build, Measure, Learn into Specify, Verify, Falsify, and it treats formal proof as the strongest form of evidence available.

**Status: working edition for review, November 2026.** This is a foundation to test and improve, not a validated claim of superiority. Claims in these documents are positions to test. Where a number is stated, the methodology says how it must be measured.

## The doctrine in brief

When generating an artifact is nearly free, the discipline moves upstream into specification and downstream into verification.

- **Specify.** Before an agent writes code, the outcome, invariants, failure modes and stop conditions are written in a form a machine can check.
- **Verify.** Each artifact is checked by mechanisms that do not trust the agent that produced it. Formal proofs come first where a property admits one, using Lean 4 as the proof assistant. Deterministic tests and reproducible builds cover the rest, and independent adversarial review covers everything else.
- **Falsify.** Each cycle tries to break the claim. Negative and inconclusive results are recorded, so no one repeats a failed search.

The working rules are seven principles: specification precedes generation; trust is not delegated to the producer; determinism is a feature; invariants beat heuristics where they exist; authority stays with a named human; cost includes checking; and sovereignty over the stack matters for high-assurance work.

The Lean Startup foundation, including validated learning and falsifiable experiments, is kept intact. Lean 4 is the intended tool for machine-checked proofs in the Verify step. Its use is a direction in this doctrine, not yet a documented result.

## Read in this order

1. [Manifesto](MANIFESTO.md): the origin, the Specify-Verify-Falsify thesis, the seven principles, and what we are not claiming.
2. [Methodology](METHODOLOGY.md): the swarm architecture of bounded personas, handoffs, Landlock sandboxing, zero-trust cryptographic gates, the deterministic commit pipeline, the four-level verification standard, and the measurements that must be established before results are claimed.
3. [Framework](FRAMEWORK.md): principles and the operating loop (Orient, Frame, Test, Verify, Decide, Retain).
4. [Field guide](FIELD-GUIDE.md): run one real learning cycle in an existing issue or work record.
5. [Cycle note template](templates/CYCLE-NOTE.md): copy only the useful parts.
6. [Practice inventory](PRACTICE-INVENTORY.md): check before treating an idea as established practice or starting overlapping work.
7. [Sources and contribution guidance](SOURCES.md): follow this when adding evidence, techniques or adaptations.

## Start here

The starting unit is one real problem, one accountable owner, one useful outcome, and the smallest safe test that could change what we do next. Planning, learning, implementation and review can overlap. Decisions should be made when the relevant context arrives, before delay creates harm or removes options.

## Verification levels

A claim is accepted only with evidence at the level it asserts.

- Level 0, observed: seen once, not evidence of reliability.
- Level 1, tested: a reproducible test passes at a recorded commit.
- Level 2, audited: an independent persona tried to falsify the claim, and the attempts are recorded.
- Level 3, proven: a machine-checked proof covers the stated property under stated assumptions.

## Relationship to Lean Startup

Eric Ries's Lean Startup provides the foundation. Lean Lab adapts it to human-agent operations. It does not claim to invent these principles, imply endorsement, or reproduce the original book. See [SOURCES.md](SOURCES.md) for the attribution record.

This repository does not supersede product-specific procedures, permissions, safety requirements or participant agreements. Product decisions remain with their owners. No license or new reuse permission is granted for external source material by citing it here.
