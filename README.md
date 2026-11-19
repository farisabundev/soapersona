# soapersona

Faris's Claude Code persona system — a Room Master/Orchestrator that routes tasks to specialized personas (Project Manager, Frontend, Backend, QA Tester, Translator, Consigliere) based on complexity, with a shared log Consigliere reviews for continuous improvement.

See `CLAUDE.md` for philosophy and setup, `agents/` for persona definitions, `skills/room` for the `/room` shortcut, `logs/` for the invocation log.

## Setup on a new machine

1. `git clone git@github.com:farisabundev/soapersona.git`
2. Symlink `agents/` into `~/.claude/agents/` and `skills/room` into `~/.claude/skills/room`
3. Add `@<path-to-this-repo>/CLAUDE.md` to your global `~/.claude/CLAUDE.md`
