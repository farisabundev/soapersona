# persona-log.jsonl schema

One JSON object per line, appended by the Orchestrator on every persona invocation.

```json
{"ts": "2026-11-19T13:40:00Z", "persona": "frontend", "model": "sonnet", "task": "short description of what was asked", "outcome": "ok", "notes": "anything Consigliere should know"}
```

`outcome` is one of: `ok`, `gate_rejected`, `issue`, `pending`.

`pending` means the persona did everything it could but couldn't fully verify the result — typically a structural blocker outside the ticket's scope (e.g. an environment/gate limitation) forced a substitute check instead of the real one. Nothing failed, so it isn't `issue`; nothing was unverified by choice or confirmed outright, so it isn't `ok` either. Use `notes` to say what was blocked and what was done instead, so a later sweep for `pending` entries knows what still needs a real check.

`notes` is where scope drift, a wrong persona pick, or an unclear brief gets recorded — this is what Consigliere reads for patterns. Empty string if there's nothing worth flagging.

Consigliere reads this periodically (not necessarily every session) to spot patterns worth raising, not line by line.

## Not tracked in git

`persona-log.jsonl` is gitignored and stays local-only — task descriptions and notes
routinely include client/project specifics (ticket numbers, people's names, business
logic) that shouldn't sit in this repo's history regardless of whether the repo is
public or private. If you need to share a pattern Consigliere found, share the specific
finding, not the raw log.
