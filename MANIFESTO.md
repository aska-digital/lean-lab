# Sovereign Agentic Neo-Lab: Manifesto

[Home](README.md) · [Framework](FRAMEWORK.md) · [Methodology](METHODOLOGY.md)

Status: working manifesto for review. Claims here are positions to test, not established results. Where this document states a number or a comparison, the methodology document says how it must be measured.

## 1. Origin

Eric Ries's Lean Startup gave builders a disciplined loop: Build, Measure, Learn. Its central insight was that a startup is a machine for learning under uncertainty, and that the cheapest way to learn is to ship the smallest thing that can falsify a belief about customers. That insight remains correct. What changed is the cost structure underneath it.

In the original loop, the expensive step was Build. Human engineers were slow, so teams had to choose carefully what to build, and the Measure step was the bottleneck that determined how many learning cycles a team could run. The loop assumed human latency everywhere: in writing code, in reviewing it, in running tests, in reading results, and in deciding what to do next.

In the agentic era that latency has collapsed. A single operator can direct many agents that write, test and review code in parallel. The bottleneck has moved. It is no longer the speed of producing an artifact. It is the speed at which the artifact can be trusted, and the speed at which a human can decide what is worth building. Generating more artifacts is now easy, and easy to mistake for progress.

The Neo-Lab idea begins here: when Build is nearly free, the discipline has to move upstream into specification and downstream into verification.

## 2. Thesis: from Build-Measure-Learn to Specify-Verify-Falsify

The Neo-Lab loop replaces the human-latency loop with three steps.

Specify. Before any agent writes code, the outcome, the invariants that must hold, the failure modes that matter, and the stop conditions are written down in a form a machine can check. A vague specification produces fast, confident, wrong output. Specification is where human judgment is most valuable and most leveraged.

Verify. Every artifact is checked against its specification by mechanisms that do not trust the agent that produced it. Verification is layered: formal proofs where the property admits them, deterministic tests and reproducible builds where it does not, and independent adversarial review for everything else. Passing tests are evidence within their coverage, not proof of correctness.

Falsify. Each cycle ends by trying to break the claim. The question is not whether the system works in the demonstration, but which assumption, if false, would change the decision, and what observation would show it. An inconclusive result is recorded as inconclusive. A negative result is kept so no one repeats the same failed search.

Specify-Verify-Falsify keeps Ries's core commitment, validated learning through falsifiable experiments, and adds two things his era could assume away: machine-checkable specifications, and verification that scales with the speed of generation.

## 3. Principles

P1. Specification precedes generation. No agent produces an artifact without a written, checkable statement of what it must do and what it must not do.

P2. Trust is not delegated to the producer. The agent that writes code is never the sole judge of that code. Independent checks run in an environment the producer cannot alter.

P3. Determinism is a feature. Given the same inputs, the pipeline should produce the same outputs. Non-determinism is a defect to be isolated and explained, not an accepted cost of working with models.

P4. Invariants beat heuristics where invariants are available. A property proven or mechanically checked is worth more than a statistical estimate that it usually holds. Heuristics remain valid where no invariant can be stated, and they must be labeled as such.

P5. Authority stays with a named human. Agents act within bounded permissions. Consequential actions, irreversible changes and access widening require a human decision recorded in the work record.

P6. Cost includes checking. The true cost of an artifact is the cost of producing it plus reviewing, verifying, repairing and maintaining it. Optimizing generation alone is a known trap.

P7. Sovereignty over the stack. Where the work is high-assurance, the team should understand and control the hardware, the runtime and the trust boundaries it depends on. Dependence on an opaque service for a property that matters is a risk to be documented, not hidden.

## 4. Relationship to the existing framework

This manifesto extends FRAMEWORK.md. The framework's operating loop (Orient, Frame, Test, Verify, Decide, Retain) still applies. The Neo-Lab adds a stronger specification step before testing, a verification standard that does not depend on the producer, and a silicon-level account of cost. Where this document and the framework conflict, the framework governs until the conflict is resolved through review.

## 5. What we are not claiming

We do not claim that agents make any team superior by default. We do not claim that a single operator can replace a research organization. We do not claim proofs for properties that have not been stated formally, and we do not claim performance figures without a baseline and a measurement method. The methodology document lists how each such claim must be established before it is made.

The ambition is narrower and testable: that disciplined specification, independent verification and deterministic pipelines let a small team deliver high-assurance work at a cost and speed that would otherwise require a much larger organization, and that this can be shown against a stated baseline.
