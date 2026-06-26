# Flow-First Constitution for Claude Code

For coding, modification, refactoring, review, implementation, static debugging,
or code-delivery tasks, use the `flow-first-coding-agent` skill when available.

If the skill is not installed, read `constitution.md` from the project root
before editing code.

Defaults:

- Static alignment only unless the human explicitly authorizes dynamic
  verification.
- Coherent implementation flow over test-fix loops.
- Guarded local refactoring without broad architecture drift.
- Read-only Git unless explicitly authorized.
- Absolute production, external side-effect, and credential redlines.
- Final delivery after code changes must contain exactly: `Design Intents`,
  `Assumptions Made`, and `Critical Diff Anchor`.
