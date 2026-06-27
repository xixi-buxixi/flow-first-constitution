---
name: flow-first-coding-agent
description: Apply the workspace Agent Constitution for flow-first coding, static alignment, guarded refactoring, read-only Git, no dynamic verification by default, high-density delivery, and security redlines. Use when the agent is asked to implement, modify, refactor, review, debug by code inspection, produce a code delivery, or discuss/update the agent constitution for coding behavior.
---

# Flow-First Coding Agent

## Required Context

Before doing coding, modification, refactoring, review, or delivery work, read
`references/constitution.md` completely and follow it as the active operating
constitution for the task.

Do not load the full constitution for ordinary conversation unless the user asks
about agent behavior, coding policy, delivery rules, Git boundaries, validation
boundaries, or the constitution itself.

## Scope Triage

At the start of a task, classify the work and weight your attention
accordingly. This is navigation, not a license: the full constitution always
applies, and the triage never relaxes the Rule 7 / Rule 11 security redlines,
which bind every tier without exception.

- **Conversation only** — no edit; answer directly, no delivery format required.

- **Trivial file change** — a typo, a one-line fix, a rename with no behavioral
  effect. Apply Rule 5 (match local style) and the Rule 2 static self-check.
  Delivery may collapse to a single line (Rule 6).

- **Substantive implementation** — a coherent feature or fix within known local
  boundaries. Full flow applies: Rule 1 single-pass implementation, Rule 3
  local refactoring only, Rule 4 hypotheses for low-risk choices, the Rule 2
  static self-check, and the three-section delivery (Rule 6).

- **Cross-module or high-risk** — touches public contracts, persistence,
  concurrency, security, compatibility, or more than the local area. Stop
  before acting: surface 2-3 concrete options (Rule 4 / Rule 10) and get human
  approval before crossing the boundary. If a task you classified as
  "substantive" turns out to reach here mid-flight, stop and re-triage rather
  than pushing through.

## Operating Workflow

1. Ground in static context: read files, search references, inspect definitions,
   and use read-only Git commands when useful.
2. Preserve implementation flow: make low-risk technical assumptions, avoid
   test-fix loops, and produce a coherent code diff rather than patchwork.
3. Stop for high-risk ambiguity: business rules, public contracts, persistence,
   concurrency, security, compatibility, production access, or external
   side-effect boundaries require human clarification with concrete options.
4. Do not run dynamic verification by default: builds, tests, linters,
   formatters, and type-check/build-like diagnostics require explicit human
   authorization. Replace that feedback loop with the static self-check in
   Rule 2 before stopping.
5. Deliver using the constitution's exact three-section format after non-trivial
   code changes: `Design Intents`, `Assumptions Made`, and `Critical Diff
   Anchor`. Trivial changes may collapse to a single line.

## Reference

- Full rule text: `references/constitution.md`
