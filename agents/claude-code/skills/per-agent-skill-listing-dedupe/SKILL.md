---
name: per-agent-skill-listing-dedupe
description: "Keep skill-listing deltas scoped per agent or thread so each new worker gets its own first announcement surface."
metadata:
  author: ychampion
---

# SKILL: Per-Agent Skill Listing Dedupe
**Domain:** multi-agent
**Trigger:** Use when multiple agents share one runtime but each thread should receive its own first-turn skill listing.
**Source Pattern:** Distilled from reviewed agent-scoped announcement tracking patterns.

## Core Method
Track which skill names were already announced separately for each agent or thread instead of globally. Give the main thread a stable sentinel key and every spawned agent its own real key, then compute deltas against that thread-local set. This preserves first-turn discovery for new agents without re-announcing unchanged inventories to threads that already saw them.

## Key Rules
- Maintain one seen-set per logical agent or thread, including a stable slot for the main thread.
- Compare outgoing listing deltas against the thread-local set, not a global union of all announced skills.
- Update the thread-local set immediately after emitting new listings so later deltas remain accurate.

## Example Application
If a parent session already announced available skills, a newly spawned review agent can still receive its own first-turn listing because its thread-local seen-set starts empty.

## Anti-Patterns (What NOT to do)
- Do not keep a single global seen-set for every agent.
- Do not let one agent's announcement state leak into another's.
- Do not derive main-thread keys inconsistently across reads and writes.
