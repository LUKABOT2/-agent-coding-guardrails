# Flip and Skip

Flip and Skip is a progress-first strategy for AI coding agents working on blocked, dynamic, or multi-entry tasks.

It combines two ideas:

- Flip: reverse direction or change entry point when the current path stalls.
- Skip: do not get trapped on one blocked item. Record it, move to the next reachable win, and return later only if progress becomes possible.

Flip and Skip is for messy terrain: long forms, lazy-loaded pages, unstable browser automation, scraping, RPA, partially available data, dependency chains, or workflows where a strict top-down order fails.

## Use when

Use Flip and Skip when the task has many items or multiple possible entry points, and rigid linear execution is causing stalls.

Best for:

- long web forms
- browser automation
- lazy-loaded or virtualised lists
- scraping workflows
- RPA tasks
- data-entry pipelines
- dependency chains
- debugging tasks with multiple possible starting points

## Core rule

Keep useful progress moving.

If the current path blocks, record the block, skip it, complete the next available win, then flip direction or use another entry point if needed.

## Prompt

```md
FLIP AND SKIP MODE.

Do not assume the task must be completed top-down.

Goal:
- maximise correct completion without stalling on blocked, hidden, slow, unloaded, or unavailable items.

Method:
- identify all viable entry points
- start from the highest-confidence entry point
- if blocked, record the blockage and skip to the next reachable item
- if the current direction stalls, reverse direction
- if another entry point exists, use it
- complete easy wins first
- retry skipped items only after other progress has been made
- do not repeat a failed strategy

Stop if:
- all items are completed
- no new progress is made after one full pass
- the same item fails twice for the same reason
- required page or system state is missing

Report:
- completed items
- skipped items
- blocked items
- direction changes used
- remaining hard blocks
```
