# soapersona

This file is meant to be imported into your global `~/.claude/CLAUDE.md` (the same way `RTK.md` is imported there) once this repo is cloned/symlinked into place.

## Philosophy

- Keep all persona output noiseless: plain language, no unnecessary jargon, unless depth is asked for.
- Route by complexity, not by habit — don't spend a high-effort pass on a low-effort task.
- Every persona invocation gets logged to `logs/persona-log.jsonl` so Consigliere can catch recurring problems.

## Git discipline

- **Any codebase personas work in (SBL included)**: no persona — including Orchestrator — commits or pushes on its own. Ever. Leave changes in the working tree and hand them back for review; Faris tests it himself (or just gives it a go) and commits/pushes on his own terms. This isn't "ask first," it's "don't do it at all."
- **This repo (soapersona) itself**: committing/pushing is fine when Faris says so in the moment — but always give him a heads-up before actually doing it, even then. Never commit or push silently just because a change looks reasonable.

## Roster

See `agents/` for the full definitions: Orchestrator, Project Manager, Frontend, Backend, QA Tester, Translator, Consigliere.

`skills/room` is a `/room` shortcut that delegates straight to Orchestrator — optional, every persona can still be addressed directly by name.

## Setup

1. Clone this repo.
2. Symlink `agents/` into `~/.claude/agents/` and `skills/room` into `~/.claude/skills/room` (or copy, if symlinking across machines is awkward).
3. Add `@<path-to-this-repo>/CLAUDE.md` to your global `~/.claude/CLAUDE.md`.
