# Bug Spray

Bug Spray is a bounded iterative repair-loop pattern for AI coding agents.

It is activated only by an explicit command. The agent works on one named bug, tests and repairs until the first defined success, records failed strategies, avoids repeats, and then stops.

Bug Spray is not an open-ended autonomous loop. It is a controlled exception to normal no-loop behaviour.

## Use when

Use Bug Spray when there is a narrow bug with an observable success condition.

Best for:

- one failing test
- a reproducible bug
- a type or lint failure
- browser automation failure
- parser or formatting mismatch
- a narrow repair where test feedback can guide the next attempt

## Activation

Use this exact form:

```md
BUG SPRAY: <task>. Success = <observable result>.
```

If `BUG SPRAY` is not explicitly present, do not run an iterative test loop.

## Prompt

```md
BUG SPRAY MODE.

Work only on the named bug.

Task:
- ...

Success:
- ...

Before editing, state:

Hypothesis:
- likely cause:
- reasonable strategies:
- planned attempts:
- hard cap:

Rules:
- Test, repair, and retry until the first success.
- Stop immediately at first success.
- Label each attempt as Attempt X of N.
- Record failed strategies in BUG_SPRAY_LOG.md.
- Read BUG_SPRAY_LOG.md before each new attempt.
- Do not repeat failed strategies.
- Do not refactor.
- Do not expand scope.
- Do not edit unrelated files.
- Do not change unrelated tests.
- Do not silence errors to force success.

Attempt limits:
- Normal cap: 10 attempts.
- Absolute cap: 20 attempts, only if justified before starting.
- Stop when planned attempts are exhausted.
- Stop if the same failure repeats twice for the same reason.

Final response only:

Changed:
- ...

Verified:
- ...

Not changed:
- ...

Notes:
- ...
```
