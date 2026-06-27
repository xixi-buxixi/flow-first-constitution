# Flow-First Constitution for Codex

For coding, modification, refactoring, review, implementation, static debugging,
or code-delivery tasks, apply the Flow-First Constitution.

If `$flow-first-coding-agent` is installed, use that skill. Otherwise read
`constitution.md` from the project root before editing code.

Core defaults:

- Triage by scope (conversation / trivial file change / substantive
  implementation / cross-module or high-risk) to weight handling; the security
  redlines bind every tier without exception.
- Use static context gathering first.
- Do not run builds, tests, linters, formatters, or type-check diagnostics unless
  the human explicitly authorizes them.
- Keep Git read-only unless the human explicitly asks for staging, commits,
  branch operations, PR creation, or push.
- Stop on production, external side-effect, credential, business-rule,
  persistence, concurrency, security, compatibility, or public-contract
  ambiguity and provide concrete options.
- After code changes, deliver exactly: `Design Intents`, `Assumptions Made`,
  `Critical Diff Anchor`.
