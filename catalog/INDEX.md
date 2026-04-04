# Curated Skill Index

This repo ships 158 curated skills selected for building or improving agentic coding CLIs, terminal tools, and multi-agent runtimes.

## Starter Bundle

- [Portable Skill Loader Progressive Disclosure](../skills/portable-skill-loader-progressive-disclosure/SKILL.md): Keep the universal skill compact yet discoverable by loading minimal frontmatter first and heavy content on demand.
- [Project-Root Scoped Local Skill Loading](../skills/project-root-scoped-local-skill-loading/SKILL.md): Resolve a stable project root first, then load local skills relative to that scope before combining them with other sources.
- [Memoized Command Source Aggregation](../skills/memoized-command-source-aggregation/SKILL.md): Load independent command sources in parallel, then memoize the merged registry by cwd so repeated lookups stay cheap and ordered.
- [Feature-Gated Command Registry Loading](../skills/feature-gated-command-registry-loading/SKILL.md): Gate optional command modules behind lazy feature checks so disabled features do not inflate startup or registry cost.
- [Lazy Heavy Command Shims](../skills/lazy-heavy-command-shims/SKILL.md): Keep heavyweight commands discoverable through lightweight shims that import the real implementation only on execution.
- [Dynamic Skill Insertion Before Builtins](../skills/dynamic-skill-insertion-before-builtins/SKILL.md): Merge runtime-discovered commands into an existing command registry by deduping them against the enabled base surface and inserting them at a stable boundary before built-in commands.
- [Layered Command Cache Invalidation](../skills/layered-command-cache-invalidation/SKILL.md): Clear every memoized layer in a command or skill pipeline so dynamic updates invalidate outer derived views as well as inner source caches.
- [Descriptive Skill Surface Admission](../skills/descriptive-skill-surface-admission/SKILL.md): Use source-aware admission rules so trusted local skills can surface automatically while plugin or MCP-provided entries must supply explicit descriptive metadata.
- [Bundled-and-MCP Turn-Zero Skill Filter](../skills/bundled-and-mcp-turn-zero-skill-filter/SKILL.md): Shrink first-turn skill listings to bundled and MCP-backed high-signal sources, with a deterministic bundled-only fallback if still too large.
- [Concurrency-Safe Tool Batching](../skills/concurrency-safe-tool-batching/SKILL.md): Group tool calls into concurrency-safe batches to run read-only calls in parallel while serializing non-read-only work.
- [Ordered Streaming Tool Execution](../skills/ordered-streaming-tool-execution/SKILL.md): Buffer and execute streaming tool calls with concurrency awareness so results appear in request order even when multiple runners overlap.
- [Progress-First Tool Emission](../skills/progress-first-tool-emission/SKILL.md): Emit progress/value updates as soon as they arrive while still buffering final results and handling cancellations or sibling errors.
- [Required Argument Aware Flag Validation](../skills/required-argument-aware-flag-validation/SKILL.md): Walk command tokens while inspecting attached/inline arguments so validators never skip missing or dangerous flag values.
- [Idempotent Tool Result Persistence](../skills/idempotent-tool-result-persistence/SKILL.md): Persist tool results once, avoid re-writing duplicates, and summarize via previews so long outputs stay accessible yet capped.
- [Conversation Engine Persistent Session State](../skills/conversation-engine-persistent-session-state/SKILL.md): Keep session-level signals (messages, read caches, memory loads) alive across turns while letting per-turn caches reset for correctness.
- [API Round Message Grouping](../skills/api-round-message-grouping/SKILL.md): Split conversation history into API-round buckets so compaction retries cut only the chunks tied to the failed round.
- [Autocompact Circuit Breaker](../skills/autocompact-circuit-breaker/SKILL.md): Break the autocompact retry loop after several consecutive failures to avoid hammering shared APIs.
- [Largest First Context Shedding](../skills/largest-first-context-shedding/SKILL.md): Reduce over-budget messages by persisting the largest fresh tool results first while leaving smaller or already-frozen blocks inline.
- [Reserved Summary Output Budget](../skills/reserved-summary-output-budget/SKILL.md): Reserve part of the context window for summary output so proactive compaction does not kill the response budget.
- [Token Budgeted Compaction With Reinjection](../skills/token-budgeted-compaction-with-reinjection/SKILL.md): Keep compaction budgets under control by compacting incrementally and reinjecting truncated attachments only when the reasoning surface remains stable.
- [Turn-Scoped Memory Prefetch with Disposal](../skills/turn-scoped-memory-prefetch-with-disposal/SKILL.md): Start a non-blocking, turn-scoped memory prefetch that auto-disposes and only injects results once per turn.
- [Session Memory First Compaction](../skills/session-memory-first-compaction/SKILL.md): Try lightweight session-memory summaries before falling back to heavyweight full-conversation compaction.
- [Additive Agent Tool Surface Construction](../skills/additive-agent-tool-surface-construction/SKILL.md): Merge agent-specific tool sets (MCP clients + fetched tools) into the parent context without disrupting the parent’s existing pool.
- [Permission Overlay Inheritance](../skills/permission-overlay-inheritance/SKILL.md): Layer child permission rules over parent session policy without dropping root-level grants or mutating shared state.
- [Forked Auto Memory Extraction](../skills/forked-auto-memory-extraction/SKILL.md): Run memory harvesting in a fenced background agent after the main turn so the primary loop stays responsive.
- [Lifecycle-Scoped Resource Cleanup](../skills/lifecycle-scoped-resource-cleanup/SKILL.md): Release every resource allocated to a child agent inside one unconditional cleanup path so finished or aborted runs leave no lingering hooks, watchers, or background jobs.
- [Fast Worktree Reuse With Head Pointer Checks](../skills/fast-worktree-reuse-with-head-pointer-checks/SKILL.md): Resume existing worktrees quickly by checking stored HEAD pointers before fetching or recreating.
- [Declarative Read Only Command Allowlists](../skills/declarative-read-only-command-allowlists/SKILL.md): Express shell-command safety as declarative flag maps so tooling knows exactly what passes.
- [Plan Mode Permission Gating](../skills/plan-mode-permission-gating/SKILL.md): Enter plan mode through an explicit permission transition that enforces a no-edit planning state before implementation.
- [Remote Safe Command Allowlist](../skills/remote-safe-command-allowlist/SKILL.md): Define a narrow explicit set of commands that stay available in remote mode because they only affect local UI state, then reuse that set at startup and after handshake refinement.
- [Bridge Origin Safe Slash Override](../skills/bridge-origin-safe-slash-override/SKILL.md): Keep remote slash-command skipping enabled by default, then reopen it only for bridge-safe commands while denying unsafe local commands with a friendly local response.
- [Shared System Init Shape Parity](../skills/shared-system-init-shape-parity/SKILL.md): Centralize `system/init` or capability payload construction in one builder so multiple transports emit identical schemas and only vary inputs or delivery.
- [Privacy-Redacted REPL Bridge System Init](../skills/privacy-redacted-repl-bridge-system-init/SKILL.md): Reuse one `system/init` payload shape across trusted and remote transports, but redact tool, MCP, and plugin metadata when the bridge path would leak local integrations or filesystem paths.
- [ANSI-Safe Border Caption Embedding](../skills/ansi-safe-border-caption-embedding/SKILL.md): Embed captions into terminal borders while preserving alignment, clipping, and color/dim semantics.
- [Wrapped Text Style Preservation](../skills/wrapped-text-style-preservation/SKILL.md): Track per-character segments so wrapped or truncated text keeps its original colors and emphasis.
- [Capability Based Spinner Glyph Selection](../skills/capability-based-spinner-glyph-selection/SKILL.md): Select spinner glyphs and colors dynamically based on terminal capability, motion preference, and stall state.

## By Category

### Command Surfaces

Skills for command registries, skill admission, discovery, and capability surfaces.

- [Budget-Aware Skill Listing Formatting](../skills/budget-aware-skill-listing-formatting/SKILL.md): Derive the active model context budget at runtime and format skill listings to fit it instead of emitting raw command sets.
- [Bundled Skill File Extraction](../skills/bundled-skill-file-extraction/SKILL.md): Lazily extract referenced files for bundled skills so large prompts stay offline until needed.
- [Bundled-and-MCP Turn-Zero Skill Filter](../skills/bundled-and-mcp-turn-zero-skill-filter/SKILL.md): Shrink first-turn skill listings to bundled and MCP-backed high-signal sources, with a deterministic bundled-only fallback if still too large.
- [CLI Command Surface Audit](../skills/cli-command-surface-audit/SKILL.md): Audit a command surface end to end so registration, discoverability, permissions, and execution all line up before shipping.
- [Classified Skill Listing Debug Telemetry](../skills/classified-skill-listing-debug-telemetry/SKILL.md): Emit low-cost debug telemetry for skill-listing batches that records batch size, initial-vs-dynamic mode, and cumulative sent count without logging the payload body.
- [Descriptive Skill Surface Admission](../skills/descriptive-skill-surface-admission/SKILL.md): Use source-aware admission rules so trusted local skills can surface automatically while plugin or MCP-provided entries must supply explicit descriptive metadata.
- [Dynamic Skill Insertion Before Builtins](../skills/dynamic-skill-insertion-before-builtins/SKILL.md): Merge runtime-discovered commands into an existing command registry by deduping them against the enabled base surface and inserting them at a stable boundary before built-in commands.
- [Feature-Gated Command Registry Loading](../skills/feature-gated-command-registry-loading/SKILL.md): Gate optional command modules behind lazy feature checks so disabled features do not inflate startup or registry cost.
- [Initial-vs-Dynamic Skill Listing Batching](../skills/initial-vs-dynamic-skill-listing-batching/SKILL.md): Mark first-time skill listings differently from later deltas so consumers can treat bootstrap exposure and updates separately.
- [Layered Command Cache Invalidation](../skills/layered-command-cache-invalidation/SKILL.md): Clear every memoized layer in a command or skill pipeline so dynamic updates invalidate outer derived views as well as inner source caches.
- [Lazy Heavy Command Shims](../skills/lazy-heavy-command-shims/SKILL.md): Keep heavyweight commands discoverable through lightweight shims that import the real implementation only on execution.
- [Local-and-MCP Skill Name Deduplication](../skills/local-and-mcp-skill-name-deduplication/SKILL.md): Merge local and MCP skill sources into one listing surface and dedupe by stable command name before announcing them.
- [Memoized Command Source Aggregation](../skills/memoized-command-source-aggregation/SKILL.md): Load independent command sources in parallel, then memoize the merged registry by cwd so repeated lookups stay cheap and ordered.
- [No-Op Empty Skill Delta Return](../skills/no-op-empty-skill-delta-return/SKILL.md): Return no attachment when an incremental skill delta has no unseen items instead of emitting a formally empty update payload.
- [Portable Skill Loader Progressive Disclosure](../skills/portable-skill-loader-progressive-disclosure/SKILL.md): Keep the universal skill compact yet discoverable by loading minimal frontmatter first and heavy content on demand.
- [Project-Root Scoped Local Skill Loading](../skills/project-root-scoped-local-skill-loading/SKILL.md): Resolve a stable project root first, then load local skills relative to that scope before combining them with other sources.
- [Resume Skill Listing Suppression](../skills/resume-skill-listing-suppression/SKILL.md): Mark the current skill listing as already sent when resuming so the transcript does not receive a redundant payload.
- [Skill Listing Reset on Real Skill Changes](../skills/skill-listing-reset-on-real-skill-changes/SKILL.md): Reset skill-listing announcement state only when the underlying skill set actually changes, not on compaction or transcript churn.
- [Skill Registry Composition and Feature Gating](../skills/skill-registry-composition-and-feature-gating/SKILL.md): Compose skill registries in fixed phases with explicit feature gates so merged command surfaces stay deterministic and cheap to refresh.
- [Skip Skill Discovery on Skill Expansion](../skills/skip-skill-discovery-on-skill-expansion/SKILL.md): Bypass skill discovery when expanded SKILL.md or generated prompt content is being reprocessed for attachments, so non-user text does not trigger recursive discovery work.
- [Skip Skill Listing Without Skill Tool](../skills/skip-skill-listing-without-skill-tool/SKILL.md): Omit skill-listing attachments for agents that do not expose the Skill tool, so discoverability context is only sent where it can be acted on.
- [Skip Skill Listing in Test Environment](../skills/skip-skill-listing-in-test-environment/SKILL.md): Suppress skill-listing attachments in test mode so discoverability noise does not interfere with deterministic test behavior.
- [Slash-Command Skill Classification Filter](../skills/slash-command-skill-classification-filter/SKILL.md): Derive a slash-command skill surface from a broader prompt-command registry by requiring descriptive metadata, excluding builtins, and admitting only a controlled set of origins plus explicit user-only commands.
- [Turn Scoped Skill Discovery Reset](../skills/turn-scoped-skill-discovery-reset/SKILL.md): Reset per-turn skill discovery tracking so long-lived sessions don’t leak outdated discovery flags while still honoring already-known skills.
- [Turn-Zero vs Inter-Turn Skill Discovery Split](../skills/turn-zero-vs-inter-turn-skill-discovery-split/SKILL.md): Block only the first discovery pass, then overlap later discovery with tool execution so streaming turns stay responsive.

### Tool Orchestration

Skills for tool batching, streaming, validation, persistence, and output shaping.

- [Atomic Post-Await State Commit](../skills/atomic-post-await-state-commit/SKILL.md): After awaiting persistence work, update the shared budget state for each `tool_use_id` exactly once so no concurrent reader ever sees a half-committed decision.
- [Budget Diminishing Continue](../skills/budget-diminishing-continue/SKILL.md): Issue continuation nudges while the turn stays under budget, then halt once diminishing returns or the budget cap justify stopping.
- [Capability Pool Resolution](../skills/capability-pool-resolution/SKILL.md): Resolve an agent’s tool intent and disallowed lists into the actual pool the agent can use, honoring wildcard, async, and teammate allowances.
- [Capability-Aware Offload Skipping](../skills/capability-aware-offload-skipping/SKILL.md): Skip generic output offload for tools whose own contracts already bound output or would become circular if wrapped again.
- [Circular-Safe Tool Registry Loading](../skills/circular-safe-tool-registry-loading/SKILL.md): Safely assemble the tool registry when optional tools have circular dependencies or heavy side effects.
- [Concurrency-Safe Tool Batching](../skills/concurrency-safe-tool-batching/SKILL.md): Group tool calls into concurrency-safe batches to run read-only calls in parallel while serializing non-read-only work.
- [Create-Only Idempotent Artifact Write](../skills/create-only-idempotent-artifact-write/SKILL.md): Persist deterministic artifacts with a create-only write and treat existing files as replay success instead of an error.
- [Decision Fate Freezing](../skills/decision-fate-freezing/SKILL.md): Freeze each tool result ID's replacement fate after it is observed so budget decisions stay deterministic across turns and forks.
- [Empty Payload Sentinel Guard](../skills/empty-payload-sentinel-guard/SKILL.md): Guard requests from closing instantly when a tool returns nothing by injecting the sentinel message and logging the event.
- [Exact Rendered Decision Journaling](../skills/exact-rendered-decision-journaling/SKILL.md): Journal each per-message tool result replacement so resume logic replays the exact preview the model saw.
- [Idempotent Tool Result Persistence](../skills/idempotent-tool-result-persistence/SKILL.md): Persist tool results once, avoid re-writing duplicates, and summarize via previews so long outputs stay accessible yet capped.
- [Modality-Preserving Binary Offload](../skills/modality-preserving-binary-offload/SKILL.md): Persist binary output with a mime-derived extension and a matching saved-file message so downstream tools keep the right modality.
- [Ordered Streaming Tool Execution](../skills/ordered-streaming-tool-execution/SKILL.md): Buffer and execute streaming tool calls with concurrency awareness so results appear in request order even when multiple runners overlap.
- [Prevent Continuation Stop Hook Messaging](../skills/prevent-continuation-stop-hook-messaging/SKILL.md): Collect stop-hook progress/errors, emit a structured prevented-continuation attachment, and summarize the block for users and logs.
- [Prevent Continuation Stop-Hook Contract](../skills/prevent-continuation-stop-hook-contract/SKILL.md): Return a narrow stop-hook result that can halt the query loop without throwing, while still surfacing blocking errors separately.
- [Preview-First Large Output Messages](../skills/preview-first-large-output-messages/SKILL.md): Persist oversized tool output once and lead with a preview plus saved-artifact reference so readers see the start without losing the full result.
- [Progress-First Tool Emission](../skills/progress-first-tool-emission/SKILL.md): Emit progress/value updates as soon as they arrive while still buffering final results and handling cancellations or sibling errors.
- [Required Argument Aware Flag Validation](../skills/required-argument-aware-flag-validation/SKILL.md): Walk command tokens while inspecting attached/inline arguments so validators never skip missing or dangerous flag values.
- [Tail-Preserving Task Output Truncation](../skills/tail-preserving-task-output-truncation/SKILL.md): Persist tool outputs alongside metadata and truncate only the preview, ensuring the header points back to the persisted replica.
- [Telemetry Sanitized Skill Invocation](../skills/telemetry-sanitized-skill-invocation/SKILL.md): Record SkillTool usage with sanitized telemetry fields so built-in, bundled, and custom skills are distinguished while avoiding PII leakage.
- [Wire-Shape Aligned Budgeting](../skills/wire-shape-aligned-budgeting/SKILL.md): Keep each wire message’s aggregate tool_result size within the configured budget by compacting the largest fresh results first.
- [Withheld Max Output Token Errors](../skills/withheld-max-output-token-errors/SKILL.md): Delay surfacing max-output-token failures until the recovery loop completes, then emit sanitized tool_result errors.

### Context Management

Skills for compaction, memory fetch, retry control, and long-running session stability.

- [API Round Message Grouping](../skills/api-round-message-grouping/SKILL.md): Split conversation history into API-round buckets so compaction retries cut only the chunks tied to the failed round.
- [API-Round PTL Retry Truncation](../skills/api-round-ptl-retry-truncation/SKILL.md): On prompt-too-long retries, drop the oldest API-round groups first and inject a synthetic user preamble when needed so the summarize request stays valid.
- [Autocompact Circuit Breaker](../skills/autocompact-circuit-breaker/SKILL.md): Break the autocompact retry loop after several consecutive failures to avoid hammering shared APIs.
- [Autocompact Recursion Guards](../skills/autocompact-recursion-guards/SKILL.md): Block autocompact from running in recursive contexts so forks and helpers don’t deadlock.
- [Cache Edit Pin and Replay](../skills/cache-edit-pin-and-replay/SKILL.md): Queue cache edits once, pin them to message positions, and replay them across turns instead of regenerating them on every retry.
- [Cache-Safe Stop-Hook Snapshotting](../skills/cache-safe-stop-hook-snapshotting/SKILL.md): Persist a cache-safe stop-hook context snapshot only for main session queries so later helpers can resume from stable state without fork pollution.
- [Compact Boundary Session Distillation](../skills/compact-boundary-session-distillation/SKILL.md): Distill the compact boundary delta into the session memory summary and the freshest user cues needed for skill capture prompts.
- [Compactable Tool Whitelist Gating](../skills/compactable-tool-whitelist-gating/SKILL.md): Only allow cached microcompact to delete tool results for a vetted, pre-gated whitelist of tool names.
- [Conversation Engine Persistent Session State](../skills/conversation-engine-persistent-session-state/SKILL.md): Keep session-level signals (messages, read caches, memory loads) alive across turns while letting per-turn caches reset for correctness.
- [Empty Trigger Short-Circuit Before App State](../skills/empty-trigger-short-circuit-before-app-state/SKILL.md): Skip nested memory collection when no triggers exist so render-bound `getAppState()` is never invoked unnecessarily.
- [Largest First Context Shedding](../skills/largest-first-context-shedding/SKILL.md): Reduce over-budget messages by persisting the largest fresh tool results first while leaving smaller or already-frozen blocks inline.
- [Main Agent Vs Background Memory Extraction Exclusion](../skills/main-agent-vs-background-memory-extraction-exclusion/SKILL.md): Skip the background memory extractor when the main agent already persisted memory during the same turn to avoid duplicates and race hazards.
- [Main Thread Only Cache Editing](../skills/main-thread-only-cache-editing/SKILL.md): Gate cached microcompact cache edits to the main thread so background forks cannot alter the shared cache state.
- [Mark-After-Filter Memory Deduplication](../skills/mark-after-filter-memory-deduplication/SKILL.md): Filter prefetched memory attachments against cumulative read state before mutating that state, so async surfacing does not dedupe itself away.
- [Media-Block Compaction Prep](../skills/media-block-compaction-prep/SKILL.md): Replace heavy media blocks with lightweight placeholders before compaction so summaries stay inside budget without losing structural cues.
- [Memory Directory Exists Guidance](../skills/memory-directory-exists-guidance/SKILL.md): Ensure memory directories exist once and surface consistent guidance so agents skip redundant mkdir calls.
- [Memory Entrypoint With Index Discipline](../skills/memory-entrypoint-with-index-discipline/SKILL.md): Keep MEMORY.md terse by capping entries, warning when caps hit, and pointing each memory to its own file.
- [Nested Memory Trigger Consume and Clear](../skills/nested-memory-trigger-consume-and-clear/SKILL.md): Process every nested-memory trigger before wiping the trigger set so subsequent iterations only see new paths.
- [Progressive Compaction Prompt](../skills/progressive-compaction-prompt/SKILL.md): Drive compaction summaries through structured prompts that sequence naming, artifacts, and invocation guidance before stripping analysis tags.
- [Reinjected Attachment Pruning Before Summary](../skills/reinjected-attachment-pruning-before-summary/SKILL.md): Prune attachments that will be regenerated after compaction so the summarizer spends budget on durable context instead.
- [Relevant Memory Selection By Header](../skills/relevant-memory-selection-by-header/SKILL.md): Rank memory files by header descriptions so only a small high-signal subset is injected back into context.
- [Reserved Summary Output Budget](../skills/reserved-summary-output-budget/SKILL.md): Reserve part of the context window for summary output so proactive compaction does not kill the response budget.
- [Role-Aware Context Slimming](../skills/role-aware-context-slimming/SKILL.md): Trim user and system context based on the agent’s role so read-only helpers don’t inherit stale git or CLAUDE metadata.
- [Session Memory First Compaction](../skills/session-memory-first-compaction/SKILL.md): Try lightweight session-memory summaries before falling back to heavyweight full-conversation compaction.
- [Time-Based Microcompact Trigger](../skills/time-based-microcompact-trigger/SKILL.md): Fall back to time-based microcompaction when the idle gap exceeds the configured threshold and directly clear the oldest compactable tool results.
- [Time-Gap Cache-Expiry Microcompact](../skills/time-gap-cache-expiry-microcompact/SKILL.md): When a long idle gap means the server cache is cold, clear old tool-result content before the next request instead of attempting warm-cache cache edits.
- [Token Budgeted Compaction With Reinjection](../skills/token-budgeted-compaction-with-reinjection/SKILL.md): Keep compaction budgets under control by compacting incrementally and reinjecting truncated attachments only when the reasoning surface remains stable.
- [Tool Success Aware Memory Suppression](../skills/tool-success-aware-memory-suppression/SKILL.md): Hide context docs for tools that already succeeded this turn while keeping guidance available for failed or unresolved tools.
- [Turn-Scoped Memory Prefetch with Disposal](../skills/turn-scoped-memory-prefetch-with-disposal/SKILL.md): Start a non-blocking, turn-scoped memory prefetch that auto-disposes and only injects results once per turn.
- [User Input Before Thread Attachments](../skills/user-input-before-thread-attachments/SKILL.md): Resolve user-input-driven attachments first, then run later attachment builders that depend on derived triggers or harvested metadata.

### Multi-Agent

Skills for child agents, forked execution, permission inheritance, and lifecycle cleanup.

- [Additive Agent Tool Surface Construction](../skills/additive-agent-tool-surface-construction/SKILL.md): Merge agent-specific tool sets (MCP clients + fetched tools) into the parent context without disrupting the parent’s existing pool.
- [Agent-Specific MCP Server Initialization](../skills/agent-specific-mcp-server-initialization/SKILL.md): Connect each agent’s frontmatter MCP servers safely and tear them down without leaking clients, while honoring plugin-only guards.
- [Append-Only Sidechain Transcripts](../skills/append-only-sidechain-transcripts/SKILL.md): Persist subagent transcripts as an append-only ordered log so forks, resumes, and sidechain readers can replay history without duplication.
- [Built-In Agent Feature Gating](../skills/built-in-agent-feature-gating/SKILL.md): Expose built-in agents according to entrypoint, mode, and feature flags so each runtime gets the right built-in surface.
- [Cache Identical Fork Prefix Construction](../skills/cache-identical-fork-prefix-construction/SKILL.md): Build forked conversation prefixes that stay identical across turns so prompt caching keeps working.
- [Cache Prefix Stability For Subagents](../skills/cache-prefix-stability-for-subagents/SKILL.md): Preserve cache-critical request fields when a child agent must share the parent's prompt prefix for cache hits.
- [Fork Child Directive Guardrails](../skills/fork-child-directive-guardrails/SKILL.md): Keep fork-decoupled workers strictly bounded by directive text and cache sharing requirements.
- [Fork Gap-Fill Reconstruction](../skills/fork-gap-fill-reconstruction/SKILL.md): Reconstruct child replacement state from local records first, then fill uncovered gaps from the parent's live map.
- [Forked Auto Memory Extraction](../skills/forked-auto-memory-extraction/SKILL.md): Run memory harvesting in a fenced background agent after the main turn so the primary loop stays responsive.
- [Forked Skill Execution With Isolated Context](../skills/forked-skill-execution-with-isolated-context/SKILL.md): Run SkillTool slash commands inside a forked sub-agent so the skill has isolated budget, telemetry, and lifecycle.
- [Hook Context Attachment Injection](../skills/hook-context-attachment-injection/SKILL.md): Collect startup hook context and inject it as metadata attachments before a child agent's first request.
- [Inherited Flags For Spawned Teammates](../skills/inherited-flags-for-spawned-teammates/SKILL.md): Propagate CLI flags/environment variables from the leader into tmux teammates so they share permission mode, plugins, and env configuration.
- [Lifecycle-Scoped Resource Cleanup](../skills/lifecycle-scoped-resource-cleanup/SKILL.md): Release every resource allocated to a child agent inside one unconditional cleanup path so finished or aborted runs leave no lingering hooks, watchers, or background jobs.
- [Main-Thread Empty-String Agent Key Normalization](../skills/main-thread-empty-string-agent-key-normalization/SKILL.md): Normalize the main thread to a concrete empty-string key so agent-scoped state maps treat main and forked threads uniformly.
- [Namespace-Resolved Skill Preloading](../skills/namespace-resolved-skill-preloading/SKILL.md): Resolve startup skill names through layered namespace lookup before preloading them as explicit visible context.
- [Orphaned Tool Call Sanitizer](../skills/orphaned-tool-call-sanitizer/SKILL.md): Remove assistant messages that reference tools without recorded results before feeding the history back into runAgent.
- [Parallelism-Aware Skill Step Design](../skills/parallelism-aware-skill-step-design/SKILL.md): Design skill steps with explicit execution topology, asking which parts run directly, in subagents, in teammate swarms, or in parallel.
- [Per-Agent Skill Listing Dedupe](../skills/per-agent-skill-listing-dedupe/SKILL.md): Track announced skills per agent or thread so each child agent gets its own first-turn capability listing instead of inheriting another thread's seen state.
- [Permission Overlay Inheritance](../skills/permission-overlay-inheritance/SKILL.md): Layer child permission rules over parent session policy without dropping root-level grants or mutating shared state.
- [Prompt-Context Handoff for Agent Runtime](../skills/prompt-context-handoff-for-agent-runtime/SKILL.md): Package prompt, identity, and runtime constraints into one explicit handoff so child agents start with the right context and no accidental leakage.
- [Session Memory Mailbox Exclusion](../skills/session-memory-mailbox-exclusion/SKILL.md): Prevent session-memory background forks from draining teammate mailbox attachments that belong to the main lead thread.
- [Subagent Metrics Bridging](../skills/subagent-metrics-bridging/SKILL.md): Connect async subagent streams to progress UI, analytics, and notifications from one finalized lifecycle snapshot.
- [Trusted Frontmatter Gating](../skills/trusted-frontmatter-gating/SKILL.md): Gate frontmatter MCP servers, hooks, and skills behind admin trust when plugin-only or hook-only modes are active.

### Extensions And MCP

Skills for extension reconciliation, MCP surfaces, and runtime activation.

- [Aggregated Change Signal Return](../skills/aggregated-change-signal-return/SKILL.md): Collapse multiple change sources into one caller-facing boolean so headless bootstraps know whether a downstream refresh is necessary.
- [Auto Refresh After New Plugin Sources](../skills/auto-refresh-after-new-plugin-sources/SKILL.md): Clear source and plugin caches, then trigger a best-effort refresh whenever reconciliation installs new sources.
- [Background Marketplace Reconciliation](../skills/background-marketplace-reconciliation/SKILL.md): Diff declared plugin marketplaces against local state, seed pending UI rows, and reconcile them in the background without blocking startup.
- [Cache Sweep Activation Fallback](../skills/cache-sweep-activation-fallback/SKILL.md): Sweep stale extension caches before activation, then fall back to a sticky manual-refresh flag if the live refresh fails.
- [Cache Warm Before Cache-Only Fanout](../skills/cache-warm-before-cache-only-fanout/SKILL.md): Warm the authoritative cache path first, then fan out cache-only readers in parallel so derived loaders never race stale state.
- [Canonical-Root Marketplace Path Normalization](../skills/canonical-root-marketplace-path-normalization/SKILL.md): Normalize relative extension source paths against a canonical repo root so shared records stay stable across worktrees.
- [Dead Path Update Skipping](../skills/dead-path-update-skipping/SKILL.md): Skip update actions that point at missing local paths when a valid materialized entry already exists, preserving the working state instead of converting drift into a noisy failure.
- [Deferred Refresh Flag Contract](../skills/deferred-refresh-flag-contract/SKILL.md): Decide when to auto-refresh plugins after marketplaces change and when to defer to a manual `/reload-plugins` via the `needsRefresh` flag.
- [Delist-After-Reconcile Enforcement](../skills/delist-after-reconcile-enforcement/SKILL.md): Enforce removals after extension synchronization and treat delisted entries as real downstream changes.
- [Diff-First Progress Projection](../skills/diff-first-progress-projection/SKILL.md): Project marketplace installation progress by diffing declared sources before kickoff so the UI shows pending spinners without waiting on the clone.
- [External Error Preserving Refresh Merge](../skills/external-error-preserving-refresh-merge/SKILL.md): Merge refresh-owned diagnostics with externally owned errors so one reload updates its slice without erasing adjacent subsystem failures.
- [Fallback Source Presence Sufficiency](../skills/fallback-source-presence-sufficiency/SKILL.md): When a declared source is only a fallback default, treat any existing materialized source as satisfying the contract instead of forcing a replacement.
- [Headless Interactive Reconcile Parity](../skills/headless-interactive-reconcile-parity/SKILL.md): Keep interactive and headless extension installation flows behaviorally aligned by sharing reconciliation logic and adapting only the outer contract.
- [MCP Skill vs Prompt Discovery Filtering](../skills/mcp-skill-vs-prompt-discovery-filtering/SKILL.md): Merge MCP-discovered prompt skills with local commands only after type filtering and name deduplication.
- [Materialization-Aware Refresh Escalation](../skills/materialization-aware-refresh-escalation/SKILL.md): React to marketplace materialization diffs by refreshing plugins when new installs land and escalating to needsRefresh when updates or refresh failures occur.
- [Mode-Gated Reconcile Skip Filter](../skills/mode-gated-reconcile-skip-filter/SKILL.md): Inject mode-specific skip rules into a shared reconciler so unsupported source types are recorded and skipped without forking the core install logic.
- [Nonblocking Plugin Install Status Projection](../skills/nonblocking-plugin-install-status-projection/SKILL.md): Map async marketplace reconciliation events into AppState rows so UIs show install/installing/failed badges without blocking.
- [Plugin-Only Agent Surface Gating](../skills/plugin-only-agent-surface-gating/SKILL.md): Prevent untrusted agent definitions from expanding the MCP surface when the session is locked to plugin-only extensions.
- [Progress Event State Bridge](../skills/progress-event-state-bridge/SKILL.md): Map background reconciliation progress events onto shared UI state so each source row reflects installing, installed, or failed.
- [Seed-Before-Diff Marketplace Registration](../skills/seed-before-diff-marketplace-registration/SKILL.md): Register seeded extension sources before diffing so bootstrap content is treated as already present.
- [Steady-State Sidecar Sync](../skills/steady-state-sidecar-sync/SKILL.md): Rebuild derived sidecar caches from authoritative extension state even when the current run made no new installs.
- [Three-Layer Extension Sync](../skills/three-layer-extension-sync/SKILL.md): Model extension lifecycle as intent, materialization, and active runtime layers, then sync each layer with dedicated transitions.

### Safety And Worktrees

Skills for safe shell execution, path guards, worktree reuse, and repo safety.

- [Auto Memory Tool Permission Fencing](../skills/auto-memory-tool-permission-fencing/SKILL.md): Gate every tool call in the auto-memory extract agent so only safe read-only actions and targeted writes execute.
- [Canonical Worktree Path Normalization](../skills/canonical-worktree-path-normalization/SKILL.md): Resolve repo-relative paths against the canonical checkout root so shared state stays stable across Git worktrees.
- [Case-Normalized Sensitive Path Guards](../skills/case-normalized-sensitive-path-guards/SKILL.md): Normalize filesystem paths and reject matches that try to spoof sensitive directories with mixed case or alternate separators.
- [Cross Shell Command Safety Maps](../skills/cross-shell-command-safety-maps/SKILL.md): Describe how to centralize cross-platform safe commands, UNC detection, and per-shell path guards so every shell tool shares the same policy.
- [Dangerous Config File Protection](../skills/dangerous-config-file-protection/SKILL.md): Keep writes out of sensitive dotfiles and `.claude` folders by checking canonicalized basenames before granting permission.
- [Declarative Read Only Command Allowlists](../skills/declarative-read-only-command-allowlists/SKILL.md): Express shell-command safety as declarative flag maps so tooling knows exactly what passes.
- [Empty Repo Bundle Preflight](../skills/empty-repo-bundle-preflight/SKILL.md): Fail fast when the repository has no refs so downstream bundling never triggers empty Git bundles.
- [Fast Worktree Reuse With Head Pointer Checks](../skills/fast-worktree-reuse-with-head-pointer-checks/SKILL.md): Resume existing worktrees quickly by checking stored HEAD pointers before fetching or recreating.
- [Plan Mode Permission Gating](../skills/plan-mode-permission-gating/SKILL.md): Enter plan mode through an explicit permission transition that enforces a no-edit planning state before implementation.
- [Reachable WIP Via Temporary Refs](../skills/reachable-wip-via-temporary-refs/SKILL.md): Capture in-flight WIP via `git stash create`, make it reachable through temporary refs, and tear down the refs after bundling finishes.
- [Remote Safe Command Allowlist](../skills/remote-safe-command-allowlist/SKILL.md): Define a narrow explicit set of commands that stay available in remote mode because they only affect local UI state, then reuse that set at startup and after handshake refinement.
- [Safe Worktree Slug Validation](../skills/safe-worktree-slug-validation/SKILL.md): Ensure Git worktree slugs can never escape the managed workspace or inject traversal.
- [Skill-Scoped Permission Suggestions](../skills/skill-scoped-permission-suggestions/SKILL.md): Suggest the narrowest permission scope by mapping a file path to its enclosing skill directory before prompting the user.
- [Staged Bundle Fallback Chain](../skills/staged-bundle-fallback-chain/SKILL.md): Retry Git bundle creation across decreasing scopes (all, HEAD, squashed) to stay under upload size limits while keeping relevant history.

### Remote And Bridge

Skills for remote-safe command surfaces, transport contracts, and bridge gating.

- [Bridge Origin Safe Slash Override](../skills/bridge-origin-safe-slash-override/SKILL.md): Keep remote slash-command skipping enabled by default, then reopen it only for bridge-safe commands while denying unsafe local commands with a friendly local response.
- [Bridge Safe Command Advertising](../skills/bridge-safe-command-advertising/SKILL.md): Advertise only slash commands that a bridge client can actually invoke by filtering announcements with the same bridge-safety predicate used at execution time.
- [Legacy Wire Name Compat Translation](../skills/legacy-wire-name-compat-translation/SKILL.md): Translate renamed internal identifiers back to their legacy wire names at serialization boundaries so patch-level consumers keep working until the planned version cutoff.
- [Nonblocking Post-Connect Capability Broadcast](../skills/nonblocking-post-connect-capability-broadcast/SKILL.md): Mark bridge sessions ready first, then send optional capability metadata asynchronously without delaying readiness.
- [Null-Hardened Feature Overrides](../skills/null-hardened-feature-overrides/SKILL.md): Validate remote numeric override maps defensively so null, non-finite, or negative flag payloads never corrupt runtime thresholds.
- [Privacy-Redacted REPL Bridge System Init](../skills/privacy-redacted-repl-bridge-system-init/SKILL.md): Reuse one `system/init` payload shape across trusted and remote transports, but redact tool, MCP, and plugin metadata when the bridge path would leak local integrations or filesystem paths.
- [Shared System Init Shape Parity](../skills/shared-system-init-shape-parity/SKILL.md): Centralize `system/init` or capability payload construction in one builder so multiple transports emit identical schemas and only vary inputs or delivery.
- [Transport Error Normalization and Retry Policy](../skills/transport-error-normalization-and-retry-policy/SKILL.md): Normalize transport failures into one retry policy so streaming bridges, sockets, and remote clients fail predictably instead of improvising recovery.
- [Type Tiered Bridge Command Gating](../skills/type-tiered-bridge-command-gating/SKILL.md): Gate bridge-executed slash commands by command type first: block local-jsx UI commands, allow prompt commands by construction, and require an explicit allowlist for plain local commands.
- [User-Invocable Capability Serialization](../skills/user-invocable-capability-serialization/SKILL.md): Serialize announced command and skill surfaces from a shared capability shape, excluding entries explicitly marked non-user-invocable.

### Terminal UI

Skills for terminal presentation, status rows, captions, and motion-aware UI.

- [ANSI-Safe Border Caption Embedding](../skills/ansi-safe-border-caption-embedding/SKILL.md): Embed captions into terminal borders while preserving alignment, clipping, and color/dim semantics.
- [Capability Based Spinner Glyph Selection](../skills/capability-based-spinner-glyph-selection/SKILL.md): Select spinner glyphs and colors dynamically based on terminal capability, motion preference, and stall state.
- [Fixed-Footprint Unicode Mascot Composition](../skills/fixed-footprint-unicode-mascot-composition/SKILL.md): Compose terminal mascots from stable spans plus swappable fragments so animated poses stay expressive without changing layout.
- [Pose-Fragment Unicode Sprite Design](../skills/pose-fragment-unicode-sprite-design/SKILL.md): Build expressive Unicode sprite systems from a stable base plus localized fragment swaps so poses stay aligned and cheap to extend.
- [Progressive Width Gated Status Rows](../skills/progressive-width-gated-status-rows/SKILL.md): Show status metadata only when the spinner row has room, shrinking entries as viewport width decreases.
- [Reduced-Motion First Terminal Animation](../skills/reduced-motion-first-terminal-animation/SKILL.md): Pause terminal animations when the user requests reduced motion, then resume cleanly without tearing the rest of the UI.
- [Scrollback Freeze Optimization](../skills/scrollback-freeze-optimization/SKILL.md): Cache and reuse animated children once they slide into scrollback so terminal resets never occur.
- [Semantic Theme-Key Rendering](../skills/semantic-theme-key-rendering/SKILL.md): Resolve semantic color keys through the active palette and contextual overrides before rendering terminal text.
- [Stall-to-Alert Color Escalation](../skills/stall-to-alert-color-escalation/SKILL.md): Blend progress colors toward an alert hue as stall intensity rises so stuck work becomes obvious without changing layout.
- [Terminal-specific Art Fallbacks](../skills/terminal-specific-art-fallbacks/SKILL.md): Layer terminal detection and fallback fragments so the same mascot identity renders correctly across Apple Terminal, xterm, and other hosts.
- [Viewport-Aware Animation Pausing](../skills/viewport-aware-animation-pausing/SKILL.md): Stop updating animation ticks as soon as the animated element leaves the viewport so scrollback never forces terminal resets.
- [Wrapped Text Style Preservation](../skills/wrapped-text-style-preservation/SKILL.md): Track per-character segments so wrapped or truncated text keeps its original colors and emphasis.
