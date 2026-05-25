# Bug Spray Task

Use only when you want a bounded repair loop for one named bug.

```md
BUG SPRAY: <task>. Success = <observable result>.

Task:
- <one narrow bug only>

Success:
- <observable success condition>

Allowed files:
- <file paths, or narrow area>

Before editing, state:

Hypothesis:
- likely cause:
- reasonable strategies:
- planned attempts:
- hard cap:

Rules:
- work only on the named bug
- label each attempt as Attempt X of N
- test, repair, and retry until first success
- stop immediately at first success
- record failed strategies in BUG_SPRAY_LOG.md
- read BUG_SPRAY_LOG.md before each new attempt
- do not repeat failed strategies
- do not refactor
- do not expand scope
- do not edit unrelated files
- stop if the same failure repeats twice

Final response:
Changed:
- ...

Verified:
- ...

Not changed:
- ...

Notes:
- ...
```
