---
name: room
description: Delegates the current task to the Orchestrator (Room Master) persona, which routes it to whichever specialized persona fits based on complexity. Use when the user types /room, or explicitly asks to "summon the room master," "use the orchestrator," or wants a task routed through the persona system instead of handled directly.
---

Delegate the user's request to the `orchestrator` subagent (defined in `agents/orchestrator.md`) using the Agent tool with `subagent_type: "orchestrator"`. Pass the user's request through as-is — Orchestrator handles briefing, routing, model-tier selection, and scope gating on its own.

This is a shortcut, not a requirement: the user can still address Frontend, Backend, QA Tester, Translator, Project Manager, or Consigliere directly by name without going through `/room`.
