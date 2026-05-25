# Agent Coding Guardrails

Practical guardrail patterns for AI coding agents that drift, bloat, loop, or improvise when they should simply do the requested work.

This repo contains three small operating patterns:

1. **Good Waiter**: scope control. Take the order, do only what was requested, bring back exactly that.
2. **Bug Spray**: bounded repair loop. Work on one named bug, record failed attempts, stop at first confirmed success.
3. **Flip and Skip**: progress-first strategy. When blocked, reverse direction, skip the jammed item, complete the next reachable win, and report the obstruction.

These are not grand frameworks. They are compact prompts and working rules for Claude Code, Codex, and similar AI coding agents.

## Quick use

Use **Good Waiter** by default.

Use **Bug Spray** only when you explicitly want a bounded test / repair loop.

Use **Flip and Skip** for dynamic, partially blocked, or multi-entry tasks such as long forms, browser automation, lazy-loaded interfaces, scraping, RPA, and messy workflows.

## Pattern files

- [`patterns/good-waiter.md`](patterns/good-waiter.md)
- [`patterns/bug-spray.md`](patterns/bug-spray.md)
- [`patterns/flip-and-skip.md`](patterns/flip-and-skip.md)

## Templates

- [`templates/good-waiter-task.md`](templates/good-waiter-task.md)
- [`templates/bug-spray-task.md`](templates/bug-spray-task.md)
- [`templates/flip-and-skip-task.md`](templates/flip-and-skip-task.md)

## One-line summary

Good Waiter controls scope. Bug Spray controls retries. Flip and Skip controls route-finding when the path is blocked.
