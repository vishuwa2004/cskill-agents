---
name: fixed-footprint-unicode-mascot-composition
description: "Build terminal mascots whose poses animate without changing layout by keeping the render footprint fixed and swapping only moving fragments."
metadata:
  author: ychampion
---

# SKILL: Fixed-Footprint Unicode Mascot Composition
**Domain:** terminal-ui
**Trigger:** Use when a terminal mascot, logo, or character should animate or emote without changing the surrounding layout.
**Source Pattern:** Distilled from reviewed fixed-grid terminal mascot rendering patterns.

## Core Method
Split the art into a stable base shell and a small set of moving fragments such as eyes, arms, or accessories. Keep every pose inside the same row-and-column footprint so the container never reflows when the pose changes. Constrain motion inside a fixed frame and clip overflow rather than letting jumps, crouches, or raised props alter nearby UI.

## Key Rules
- Keep width and height identical across every pose so surrounding status lines, borders, and prompts never shift.
- Store stable background and body segments separately from movable fragments so animation swaps only the pieces that actually move.
- Render inside a fixed-height frame and clip overflow so vertical motion feels animated without affecting layout.

## Example Application
If a CLI splash header uses a mascot that should wink during loading and celebrate after success, build both poses on top of the same base body and frame so the header remains perfectly aligned.

## Anti-Patterns (What NOT to do)
- Do not let different poses add or remove columns or rows.
- Do not rebuild the full art every frame when only a few fragments changed.
- Do not let animated parts spill into adjacent lines and corrupt the prompt.
