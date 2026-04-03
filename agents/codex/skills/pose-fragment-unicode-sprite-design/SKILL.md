---
name: pose-fragment-unicode-sprite-design
description: "Compose Unicode sprite poses by swapping localized fragments so expressions and gestures share one stable silhouette and spacing."
metadata:
  author: ychampion
---

# SKILL: Pose-Fragment Unicode Sprite Design
**Domain:** terminal-ui
**Trigger:** Use when a terminal sprite needs multiple expressions or gestures while staying anchored to the same silhouette.
**Source Pattern:** Distilled from reviewed fragment-swapped terminal sprite systems.

## Core Method
Define the sprite as a stable body plus a pose dictionary for the small fragments that change between expressions. Each pose reuses the same base spacing and shell while swapping only localized pieces such as eyes, hands, or held objects. This keeps rendering cheap, makes new poses easy to add, and prevents subtle alignment drift.

## Key Rules
- Keep the immutable shell in one shared structure and isolate all pose-specific fragments in a separate mapping.
- Swap only localized fragments so new poses never require re-deriving the full sprite layout.
- Design fallback fragments for terminals that cannot render the fanciest glyphs without changing spacing.

## Example Application
For a coding assistant banner with neutral, alert, and celebration poses, keep one base sprite and store only the changing face and arm fragments per pose.

## Anti-Patterns (What NOT to do)
- Do not author every pose as a fully separate ASCII block.
- Do not tie pose changes to width or padding changes.
- Do not rely on terminal-specific glyphs without a same-width fallback.
