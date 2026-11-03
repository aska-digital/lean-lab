# Practice inventory

[Home](README.md) · [Sources](SOURCES.md)

The goal is to capture everything valuable in our operations over time. This first inventory covers only the sources reviewed for this proposal. A document describing a procedure proves that it is documented, not that it is consistently followed or effective. No measured improvement from Sleek Startup has been established here.

## Evidence states

- **Documented practice:** a source states how work should operate; adoption and results may still need checking.
- **Observed instance:** a specific artifact or event shows the practice was used in that instance.
- **Tested locally:** a defined comparison supports a result within stated limits.
- **Proposed adaptation:** a mechanism to try, not an established result.
- **Open gap:** a potentially valuable area without sufficient reviewed evidence.

These states are not a mandatory maturity ladder. A tested practice can fail elsewhere. Record evidence, context and counterexamples rather than assign a prestige score.

## Initial map

| Practice or mechanism | Source and status at 2026-11-03 | Framework use | What remains unproved |
| --- | --- | --- | --- |
| Canonical implementation home; preserve ownership; review downstream integration separately | Exo repository workflow [S2], documented practice | Framework principles 5–6 | Frequency of adherence and reduction in duplicate effort |
| Independent review of the exact head; distinguish merge, integration and live use | Exo repository workflow [S2], documented practice | Principles 5–6 and cycle result field | Effect on defects and total lead time across projects |
| Keep consequential choices open until relevant, with triggers and reversible defaults | Compass PR #12 [S3], proposed guidance in an open PR | Principle 2 | Adoption and benefit in real product decisions |
| Traceable small end-to-end slices; test contracts before generalizing | Compass roadmap [S4], documented proposal, not completed capability | Principles 4 and 7 | Implementation, actual use and portability |
| Record review findings as documentation corrections with regression tests | Exo #1119 merge [S5], observed instance | Principles 6–7 | Whether this is representative and its net maintenance benefit |
| Explicit scope, evidence-bearing handoffs and resource limits for agent work | Proposed adaptation in this framework | Principles 3 and 5 | Which fields prevent failures without adding excessive overhead |
| Compare agent workflows on accepted outcomes and full review/rework cost | Proposed adaptation in this framework | Field guide | Quality/cost tradeoffs on real task sets |
| Bound parallel work by integration and review capacity | Proposed adaptation, informed by S2's ownership rules | Principle 5 | Useful limits for each team and task type |

Source identifiers refer to [SOURCES.md](SOURCES.md). Each row identifies what can actually be claimed. A linked source does not imply that its maintainers have adopted this framework.

## Coverage still to investigate

Do not assume the following are absent from operations. They have not been mapped in this first pass:

- Customer discovery, demand tests, pricing, distribution, sales and retention.
- Opportunity selection, research ingestion, attribution and technology-fit assessment.
- Portfolio choices, capital allocation and stopping low-value initiatives.
- Agent/model routing, evaluation suites, context continuity and knowledge retrieval.
- Incident response, support, maintenance, release and downstream verification.
- Collaboration agreements, contributor recognition, governance and participant agency.
- Personal and team workflows, scheduling, communication and attention management.

For each area, locate a permissioned source and a concrete example before writing a general rule. Keep sensitive commercial, personal or operational details in their authorized home. A public abstraction must not reveal a private case through names, examples or linked access.

## How to add a practice

Record: problem solved; actual mechanism; owner and context; source/version/date; evidence state; costs and failure modes; boundary conditions; observed results or missing measurements; and the smallest next test. Link existing procedures rather than copying and diverging from them. Ask whether the mechanism should be reused, changed, retired or kept local.

Do not promote a founder preference, a polished proposal, an agent's confidence or a single success into a proven universal practice. Capture useful failures too. When an operational source changes, revisit the mapping. Product-specific procedures remain authoritative in their own scope.

## First validation work

Choose one real workflow and owner when they are available. Use the field guide to establish a baseline, run a bounded comparison, and record the result here with its limits. No pilot, budget, person or deadline is assigned by this document. The immediate open decision is which existing workflow has enough evidence and review capacity to make a first test worthwhile.
