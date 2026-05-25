# Flip and Skip Task

Use when rigid top-down execution is failing or likely to fail.

```md
FLIP AND SKIP MODE.

Task:
- <task with many items, dynamic loading, blocked steps, or multiple entry points>

Goal:
- <observable completion target>

Entry points:
- <top / bottom / goal state / known loaded region / other>

Rules:
- do not assume top-down order is best
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
