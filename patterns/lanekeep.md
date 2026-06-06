# LaneKeep AutoP

Active workflow: Focus exclusively on the assigned issue/ticket. Do not touch unrelated code unless explicitly authorised.

## Mode definition

LaneKeep = AutoP + Hold List.

AutoP: Narrow autonomous execution, like a good waiter, serving only what was ordered.

Hold List: Keep safe work moving, hold uncertain or risky actions for later human review.

## Purpose

Remove the need for constant human authorisation while avoiding scope creep, risky execution, and hidden regressions.

## Core rules

1. Strict scope: Stay inside the stated task.
2. MVP first: prefer the smallest working patch over redesign.
3. Minimal blast radius: change only what proves the outcome.
4. Hold list: do not pause the whole workflow; hold only ambiguous or risky actions.
5. Silent local action: perform safe, reversible, local changes without prompting.
6. Fail-safe stopping: halt immediately for protected branches, production settings, destructive commands, unclear scope, or data risk.
7. Safety pre-flights: use versioning and checkpoints before risky edits.
8. Dual-agent sync: cross-check only when touching shared boundaries or integration files.
9. Terse comms: logs must be short and actionable.
10. Test ceiling: maximum 3 directed proof tests.

## Authority matrix

Allowed autonomously

- inspect repo files and architecture
- read-only navigation and search tools (pwd, ls, rg, grep, head, tail)
- git status/diff/branch/log
- local read-only diagnostics or linters
- targeted offline unit tests specific to the modified files
- create a narrow short-lived local feature branch
- scoped code edits
- verify changes with explicit boundary diffs
- recover from cwd errors and retry

Allowed only for safety/recovery

- create backup branch before risky edits
- make a local backup copy of a config/state
- inspect previous stable commit
- revert last local change when it breaks compilation or the proof
- stop and report if manual rollback is safer than patching

Explicit approval required

- pushing to remote or protected branches (main/master/release) or production environments
- database schemas, migrations, or live data changes
- credentials, secrets, auth/security behaviour
- CI/CD or deployment changes
- broad refactoring or architecture changes
- continuing after an out-of-scope regression

## Safety pre-flights

Before modifying files, verify and record:

- git status --short
- current branch
- intended target files

If the change touches shared files, create/confirm a named branch and minimise impact.

## Tests

Run only tests directly tied to the change.

Do not run full suites unless explicitly required.

Maximum 3 directed tests.

## Stop conditions

Stop autonomous execution and report when:

- MVP proof passes
- 3 directed tests reached
- protected boundary encountered
- evidence contradicts plan
- ambiguity threatens instability
- permissions block execution after one recovery attempt

## Hold List

Do not stop the task because one action needs approval.

Continue safe work. Hold actions that may exceed scope or create risk, and present them in a numbered list.

Hold examples

- scope expansion
- shared critical files
- destructive commands
- protected branch pushes
- security/credentials
- production environment
- unclear requirements

Held action format

1. Action
   Reason
   Risk: Low / Medium / High
   Required for completion: Yes / No

2. Action
   Reason
   Risk: Low / Medium / High
   Required for completion: Yes / No

Human review rules

- Approve numbers to execute.
- Reject numbers to skip.
- Unselected numbers are rejected by default.
- Rejected items must be reverted or left inactive.

If there are more than 4 held actions, give a short confirmation first, then show the list.

## Completion report

active workflow:
branch:
task:
files inspected:
files changed:
functions/modules changed:
MVP outcome:
tests run:
cross-check needed:
production touched:
CI/CD touched:
database modified:
protected boundaries preserved:
scope creep detected:
concerns/blockers:
one next allowed action:
LaneKeep complete:
