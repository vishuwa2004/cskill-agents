---
name: tool-success-aware-memory-suppression
description: "Suppress contextual docs or memories for tools that already succeeded in the current turn while keeping help available for failed or unresolved tools."
metadata:
  author: ychampion
---

# SKILL: Tool-Success-Aware Memory Suppression
**Domain:** context-management
**Trigger:** Use when memory or help attachments should focus on tools the model is still struggling with instead of tools already working reliably this turn.
**Source Pattern:** Distilled from reviewed recent-tool-outcome memory selection heuristics.

## Core Method
Scan the current human-turn window, pair tool invocations with their results, and promote a tool into the suppression set only if it has successful results and no failures in that window. Keep docs eligible when any failure occurred or when the result is still unresolved. This lets context injection spend budget on the tools currently causing trouble instead of repeating help for tools the model is already using correctly.

## Key Rules
- Bound the scan to the current human-turn window so old successes do not suppress help for a new problem.
- Treat any failure as a reason to keep the tool eligible for docs or memory.
- Do not suppress tools whose current outcome is still unknown.

## Example Application
If the model used two read-only tools successfully this turn but keeps failing with a shell or edit tool, suppress guidance for the successful tools and keep help attached for the failing one.

## Anti-Patterns (What NOT to do)
- Do not suppress help merely because a tool was invoked.
- Do not let an earlier success hide docs after a later failure.
- Do not carry success suppression across unrelated turns.
