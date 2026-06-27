# Flow-First Constitution

A high-density constitution for AI coding agents that prioritizes creation flow,
static alignment, guarded local refactoring, read-only Git defaults, and strict
production/security redlines.

This repository packages the same operating model for multiple AI coding tools:
Codex, Cursor, Windsurf, Claude Code, and Google Antigravity.

## What It Changes

- Prefer coherent implementation flow over red-green test-fix loops.
- Forbid builds, tests, linters, formatters, and type-check diagnostics unless
  the human explicitly authorizes them, and replace that feedback loop with a
  mandatory static self-check before delivery.
- Allow static context gathering: file reads, reference search, type inspection,
  config reads, project-structure reads, and read-only Git.
- Permit local elegance and directly related cleanup while blocking broad
  architecture drift without approval.
- Require high-risk ambiguity to stop with concrete options.
- Keep Git staging, commits, branches, checkout/reset/stash, PRs, and pushes
  under human control by default.
- Refuse production, remote side-effect, external API, and credential leakage
  risks.

## Repository Layout

```text
constitution.md
skills/flow-first-coding-agent/
adapters/
  codex/AGENTS.md
  cursor/.cursor/rules/flow-first-constitution.mdc
  claude-code/CLAUDE.md
```

- `constitution.md` is the canonical rule text for human review.
- `skills/flow-first-coding-agent/` is the single, portable Agent Skill package.
  Every skill-based tool (Codex, Windsurf, Claude Code, Antigravity) installs
  this same package; the repository does not keep per-tool skill copies.
- `adapters/*` contains only the thin, tool-specific entrypoints that cannot be
  expressed as the shared skill: an `AGENTS.md` for Codex, a `.mdc` rule for
  Cursor, and a `CLAUDE.md` memory entry for Claude Code. None of them duplicate
  the full rule text.

## Codex

Codex can use the skill package directly.

```powershell
Copy-Item -Recurse .\skills\flow-first-coding-agent $env:USERPROFILE\.codex\skills\
```

For project-local instructions, copy:

```text
adapters/codex/AGENTS.md -> AGENTS.md
constitution.md -> constitution.md
```

The skill uses progressive disclosure: metadata triggers the skill, `SKILL.md`
loads first, and the full constitution is loaded only from
`references/constitution.md` when coding/review/delivery work requires it.

## Cursor

Copy the Cursor project rule and the canonical constitution into a project:

```text
adapters/cursor/.cursor/rules/flow-first-constitution.mdc
constitution.md
```

The rule is Agent-Requested, not always-on: it omits `globs` and is loaded by
description relevance for coding, refactoring, review, implementation, and
code-delivery tasks.

## Windsurf

Windsurf supports Agent Skills. Install the shared skill package into the
location your Windsurf setup uses for local skills, for example:

```text
skills/flow-first-coding-agent -> .windsurf/skills/flow-first-coding-agent
```

The skill preserves progressive disclosure by keeping the full constitution in
`references/constitution.md`.

## Claude Code

Use the shared skill package, plus an optional memory entrypoint:

```text
skills/flow-first-coding-agent -> <project-or-user>/.claude/skills/flow-first-coding-agent
adapters/claude-code/CLAUDE.md -> CLAUDE.md
```

Copy the skill into a project or user-level Claude Code skills directory. Copy
`CLAUDE.md` only when you also want the constitution advertised as project
memory.

## Antigravity

Google Antigravity can consume Agent Skills. Install the shared skill package
into your project or ecosystem skills directory, for example:

```text
skills/flow-first-coding-agent -> .agent/skills/flow-first-coding-agent
```

For shared ecosystem/global-style skill directories, use the `.agents/skills/`
location your Antigravity setup expects. The official spelling is `antigravity`;
note the common prompt typo `antigrativity`.

## Maintenance Rules

- Edit the canonical rules in `constitution.md` first.
- Keep `skills/flow-first-coding-agent/references/constitution.md` synchronized
  with the canonical text. These are the only two copies of the rule text in the
  repository; the skill copy exists solely to support progressive disclosure.
- Keep tool adapters thin: an adapter holds only its tool-specific entrypoint and
  must never embed the full 11 rules. Every adapter points at the shared skill or
  the canonical `constitution.md`.
- Do not add per-tool skill copies. All skill-based tools install the single
  package under `skills/`.
- Do not add scripts unless deterministic automation becomes necessary.
- Do not run dynamic verification unless the human explicitly asks for it.

## References

- Codex skills and AGENTS.md: https://developers.openai.com/codex/skills and https://developers.openai.com/codex/guides/agents-md
- Cursor rules: https://cursor.com/docs/context/rules
- Windsurf Agent Skills: https://docs.windsurf.com/windsurf/cascade/skills
- Claude Code memory and skills: https://docs.anthropic.com/en/docs/claude-code/memory and https://docs.anthropic.com/en/docs/claude-code/skills
- Google Antigravity Agent Skills: https://antigravity.google/docs/skills
