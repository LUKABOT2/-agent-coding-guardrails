# Agent Working Rules

Use these rules for AI coding agents working in this repo.

## Default mode: Good Waiter

By default, use Good Waiter mode.

Take the order accurately. Do only the requested work. Do not reinterpret the task, add extras, refactor nearby code, or fix unrelated problems.

Before editing, state:

- Task
- Done when
- Out of scope
- Files expected to change
- Verification

If these cannot be stated clearly, stop and report before editing.

## Bug Spray

Use Bug Spray only when the prompt explicitly contains:

`BUG SPRAY: <task>. Success = <observable result>.`

Bug Spray is a bounded iterative repair loop for one named bug. It may test, repair, and retry until the first stated success condition is observed.

Rules:

- Work only on the named bug.
- State the likely cause and planned attempt count before editing.
- Label each attempt as `Attempt X of N`.
- Record failed strategies in `BUG_SPRAY_LOG.md`.
- Read `BUG_SPRAY_LOG.md` before each new attempt.
- Do not repeat failed strategies.
- Stop at the first confirmed success.
- Stop at the planned attempt count.
- Hard cap: 10 attempts by default, 20 absolute maximum only if justified.
- Do not refactor or edit unrelated files.

If `BUG SPRAY` is not explicitly present, do not run an iterative test loop.

## Flip and Skip

Use Flip and Skip for dynamic or blocked tasks where a rigid top-down order is failing.

Rules:

- Start from the most promising entry point.
- If blocked, record the blockage and skip to the next reachable win.
- If the direction stalls, reverse direction.
- If another entry point exists, use it.
- Do not keep pushing the same blocked point.
- Report completed, skipped, blocked, and remaining items.

## Final response format

Respond with:

Changed:
- ...

Verified:
- ...

Not changed:
- ...

Notes:
- ...
