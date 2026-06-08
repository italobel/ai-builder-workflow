---
name: create-plan
description: "Turn a fully explored set of requirements into a phased, testable markdown plan with status tracking. Each phase is small enough to verify on its own. Use after /explore when the user wants to break a feature into steps, or says things like 'plan this out', 'break this into steps', 'create a task breakdown', or '/create-plan'."
---

# create-plan

The goal is to turn what was clarified in /explore into a structured plan that can be worked phase by phase. Not one big plan. Not a wish list. A real, ordered sequence where each phase ends in something testable.

The single most common mistake non-technical builders make is asking the agent to "do the whole thing." This skill exists to make that mistake impossible by enforcing the phase discipline.

## When to use this

- Immediately after /explore, once the scope and unknowns are settled.
- When the user says "plan this", "break this into phases", or "/create-plan".
- Before any code is written.

If exploration has not happened, suggest /explore first. Do not skip it.

## What it does

1. Reviews the explored scope: what is being built, what is out of scope, what technical decisions were made.
2. Breaks the work into three to five phases. Each phase should be independently testable.
3. Lists subtasks under each phase — three to five per phase, specific and actionable.
4. Saves the plan as a markdown file the user can track (e.g., `PLAN.md`).
5. Shows the user the plan and asks for confirmation.

## What makes a phase "good"

- Small enough that you can finish it, test it, and decide whether to keep going.
- Has a clear deliverable (a feature works, a migration runs, a deploy completes).
- Does not depend on a later phase to be testable.
- Named by outcome, not by activity ("User authentication," not "Add auth code").

If you cannot test a phase on its own, the phase is too big. Split it.

## Output template

```markdown
# {Feature} Implementation Plan

**Overall Progress:** `0%`

## TL;DR
{One-paragraph summary of what we are building and why}

## Critical decisions
- **{Area}:** {choice} — {brief rationale}

## Out of scope
- {Things explicitly deferred}

## Phases

### Phase 1: {Name}
- [ ] **Step 1: {Outcome}**
  - [ ] {Subtask}
  - [ ] {Subtask}

### Phase 2: {Name}
- [ ] **Step 2: {Outcome}**
  - [ ] {Subtask}
  - [ ] {Subtask}

## Notes
- {Anything important to remember}
```

## Behavior rules

- No scope creep. Only include what was discussed in /explore.
- Three to five phases is the sweet spot. More than five usually means a phase is too small.
- Save the plan as a file the user can refer to and that /execute can read.
- After saving, tell the user the next step is /execute.
