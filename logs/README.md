# persona-log.jsonl schema

One JSON object per line, appended by the Orchestrator on every persona invocation.

```json
{"ts": "2026-11-19T13:40:00Z", "persona": "frontend", "model": "sonnet", "task": "short description of what was asked", "outcome": "ok", "notes": "anything Consigliere should know"}
```

`outcome` is one of: `ok`, `gate_rejected`, `issue`.

`notes` is where scope drift, a wrong persona pick, or an unclear brief gets recorded — this is what Consigliere reads for patterns. Empty string if there's nothing worth flagging.

Consigliere reads this periodically (not necessarily every session) to spot patterns worth raising, not line by line.
