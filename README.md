# Flow-First Constitution

A high-density constitution for AI coding agents that prioritizes creation flow,
static alignment, guarded local refactoring, read-only Git defaults, and strict
production/security redlines.

This repository packages the same operating model for multiple AI coding tools:
Codex, Cursor, Windsurf, Claude Code, and Google Antigravity.

## What It Changes

- Prefer coherent implementation flow over red-green test-fix loops.
- Forbid builds, tests, linters, formatters, and type-check diagnostics unless
  the human explicitly authorizes them.
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
  codex/
  cursor/
  windsurf/
  claude-code/
  antigravity/
```

- `constitution.md` is the canonical rule text for human review.
- `skills/flow-first-coding-agent/` is the portable Agent Skill package.
- `adapters/*` contains tool-specific entrypoints that load or point to the
  constitution without duplicating the full rule text where the tool permits it.

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

The Codex skill uses progressive disclosure: metadata triggers the skill,
`SKILL.md` loads first, and the full constitution is loaded only from
`references/constitution.md` when coding/review/delivery work requires it.

## Cursor

Copy the Cursor project rule and the canonical constitution into a project:

```text
adapters/cursor/.cursor/rules/flow-first-constitution.mdc
constitution.md
```

The rule is not always-on. It is described for coding, refactoring, review,
implementation, and code-delivery tasks so Cursor can load it when relevant.

## Windsurf

Windsurf supports Agent Skills. Copy the packaged skill into a project:

```text
adapters/windsurf/.windsurf/skills/flow-first-coding-agent
```

Or install the shared skill package into the location your Windsurf setup uses
for local skills. The skill preserves progressive disclosure by keeping the full
constitution in `references/constitution.md`.

## Claude Code

Use the Claude Code skill package and optional memory entrypoint:

```text
adapters/claude-code/.claude/skills/flow-first-coding-agent
adapters/claude-code/CLAUDE.md
```

Copy `.claude/skills/flow-first-coding-agent` into a project or user-level
Claude Code skills directory. Copy `CLAUDE.md` only when you also want the
constitution advertised as project memory.

## Antigravity

Google Antigravity can consume Agent Skills. For project-local use, copy:

```text
adapters/antigravity/.agent/skills/flow-first-coding-agent
```

For shared ecosystem/global-style skill directories, use:

```text
adapters/antigravity/.agents/skills/flow-first-coding-agent
```

The adapter directory uses the official spelling `antigravity`; this README also
mentions the common prompt typo `antigrativity`.

## Maintenance Rules

- Edit the canonical rules in `constitution.md` first.
- Keep `skills/flow-first-coding-agent/references/constitution.md` synchronized.
- Keep tool adapters thin; do not duplicate all 11 rules in every adapter.
- Do not add scripts unless deterministic automation becomes necessary.
- Do not run dynamic verification unless the human explicitly asks for it.

## References

- Codex skills and AGENTS.md: https://developers.openai.com/codex/skills and https://developers.openai.com/codex/guides/agents-md
- Cursor rules: https://cursor.com/docs/context/rules
- Windsurf Agent Skills: https://docs.windsurf.com/windsurf/cascade/skills
- Claude Code memory and skills: https://docs.anthropic.com/en/docs/claude-code/memory and https://docs.anthropic.com/en/docs/claude-code/skills
- Google Antigravity Agent Skills: https://antigravity.google/docs/skills
