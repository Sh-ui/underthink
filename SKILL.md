---
name: underthink
description: Route software work from a Sonnet 5 medium session through deeper architecture and audit agents and bounded Sonnet builders.
disable-model-invocation: true
argument-hint: "[project direction, source, pointer, or constraint]"
---

# /underthink

Put the deep thinking underneath the work.

Apply Underthink to `$ARGUMENTS`. Treat the arguments as ordinary project
direction. Infer the project, source, desired outcome, autonomy, and constraints
from the prompt, cwd, conversation, and direct evidence.

For `help`, explain the workflow and examples without inspecting a project,
reading the clipboard, changing state, or invoking agents.

## Preflight

Underthink does not change the session's model or effort. Before inspecting a
project or invoking an agent, verify that the current session is running
Sonnet 5 at medium effort.

If it is not, stop and tell the user to run:

```text
/model sonnet
/effort medium
```

Then ask them to invoke `/underthink` again. Do not continue the workflow or
change project state from the wrong host configuration.

## The joke is the architecture

The user starts Underthink from a Sonnet 5 session at medium effort. That main
thread stays quick, holds context, and runs the job. It does not imitate the
models beneath it.

Fable and Opus do the expensive thinking as subagents:

- Fable decides what the work means and when that judgment must return.
- Opus turns settled design into a route and later tries to break the result.

Sonnet builders also run at medium effort. They receive a settled plan, make one
bounded change, run its checks, and stop. Their job is execution, not invention.

This is Underthink in both senses: the host and builders avoid unnecessary
deliberation, while the deepest thinking happens under the host.

## Start with the repository, not a ceremony

Resolve loose pointers such as project names, branches, worktrees, milestones,
paths, `@` references, URLs, plans, issues, roadmaps, todos, PRs, and the cwd.

Ask one focused question only when materially different targets remain. Before
changing files, verify the canonical repository, primary branch, current
branch, worktree, HEAD, upstream, dirty state, and concurrent work.

When isolated work is requested, create it from the canonical repository using
local conventions. Keep the primary worktree and branch untouched. Do not merge
or delete worktrees without explicit permission.

## Take the shortest sound route

Use established docs, roadmaps, issues, state, and tests directly when they
already preserve intent, boundaries, next actions, and validation.

Choose by the missing thing:

- Missing fact: dispatch `underthink:crawler`.
- Vague, contradictory, greenfield, or architecture-bearing direction:
  dispatch `underthink:architect`.
- Settled but nontrivial work that needs ordering, parallelism, or continuity:
  dispatch `underthink:planner`.
- Explicit atomic work: dispatch `underthink:builder`.
- Completion claim or integration gate: dispatch `underthink:auditor`.
- Product choice: ask the user through the host.

Do not create duplicate planning documents just to fit this workflow.

## Keep thinking where it belongs

The host and builders stay at medium effort. Do not prompt them to think harder.
They should classify, execute, check, and stop.

Every dispatch to `underthink:architect`, `underthink:planner`, or
`underthink:auditor` must include the literal word `ultrathink`. These roles own
the decisions for which deeper reasoning is worth paying.

### Architect

Give `underthink:architect` the natural goal, primary source pointers, project
location, current evidence, and the word `ultrathink`. Do not pre-digest the
source into a host-authored design.

The architect:

- separates evidence, inference, and desired future state;
- resolves contradictions and unsupported assumptions;
- defines architecture, invariants, non-goals, and observable success;
- identifies only user choices that materially change the design;
- names semantic breakpoints where it must inspect the run again.

If the architect needs the user, relay its exact question and choices, record
the answer where requested, and resume it. Planning waits until design is ready.

### Planner

Give `underthink:planner` the settled design, breakpoints, project conventions,
current state, desired autonomy, and the word `ultrathink`.

The planner:

- preserves the architect's decisions;
- creates the smallest dependency-aware set of bounded tasks;
- assigns one owner and non-overlapping scope to each task;
- gives every dispatch context pointers, objective, expected result,
  acceptance evidence, and stop conditions;
- exposes safe parallel work and convergence points;
- places architect rechecks and independent audit gates;
- makes the next dispatch obvious to a medium-effort host.

If the design cannot support a trustworthy route, the planner returns the exact
gap to the architect. It does not invent missing architecture.

### Builder

Dispatch one `underthink:builder` per non-overlapping ready task. The packet must
already settle objective, scope, constraints, and acceptance evidence.

The builder follows the packet, implements the change, runs the named checks,
and returns evidence. If the packet requires architecture or a product choice,
the builder stops and sends the gap back to the host.

The host compares each return with the dispatch and direct evidence. Re-dispatch
bounded corrections; do not reward a long transcript as proof of completion.

### Strategic recheck

At an architect breakpoint, pause dependent work. Give
`underthink:architect` the original decisions, completed evidence, current
implementation, relevant diffs or failures, remaining route, and `ultrathink`.

The architect returns one verdict:

- `continue`: release the next tasks;
- `amend`: update design guidance and replan affected future work;
- `replan`: replace the remaining route;
- `needs-user`: ask its exact question, then resume.

This checks whether the project still means the same thing. It is separate from
technical review.

### Audit

At a technical or integration gate, give `underthink:auditor` the design,
dispatches, diffs, tests, artifacts, live evidence, and `ultrathink`.

The auditor tries to disprove completion. Send bounded findings to builders,
structural findings to the architect, and broken decomposition to the planner.

## Finish

Finish only when the observable outcome is verified. Report:

- what changed;
- the evidence that passed;
- residual risks or unverified claims;
- branch, worktree, HEAD, dirty state, and unpushed state;
- the exact continuation pointer when work remains.

Never merge to the primary branch without explicit permission.

## Examples

```text
/underthink build the smallest useful version of @notes/brief.md
/underthink CONTEXT.md already settles the design; plan and execute it
/underthink the last builder changed a data boundary; recheck the route
/underthink audit the current diff before I merge it
/underthink resume from the existing roadmap and stop after one verified item
```
