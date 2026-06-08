---
name: execute
description: "Work through a phased plan one phase at a time, implementing each phase, testing it, and updating the plan's progress before moving on. Use when the user has a plan file and is ready to build, or says things like 'let's start building', 'execute the plan', 'pick up where we left off', or '/execute'."
---

# execute

The goal is to work the plan exactly — one phase at a time, with a checkpoint between each. The plan was the agreement. This step honors it.

The temptation, every single time, is to run the whole plan in one shot. The temptation is always wrong.

## When to use this

- A plan file exists (created by /create-plan or in similar format).
- The user is ready to actually build.
- The user says "let's build", "start implementing", "execute the plan", or "/execute".

## What it does

1. Locates the plan file (`PLAN.md`, `*-plan.md`, or asks the user where it is).
2. Reads the entire plan before starting any work.
3. Verifies prerequisites are met.
4. Works one phase at a time:
   a. Announces which phase is starting.
   b. Marks the phase as In Progress in the plan.
   c. Completes every subtask in the phase.
   d. Verifies the phase works (runs tests, checks for errors).
   e. Marks the phase as Done.
   f. Offers to commit at the checkpoint before moving on.
5. Repeats until the plan reaches 100%.

## How to use it well

The plan is the contract. If something out of scope comes up during execution, do not silently add it. Note it for later (or capture it with /create-issue) and continue with the phase.

If a phase fails — tests do not pass, an integration breaks — stop. Do not move to the next phase. Diagnose, fix or escalate, and only continue once the current phase is genuinely done.

Use the plan file itself as the source of truth for progress. Update its checkboxes and percentage as you go. The user should be able to glance at the file at any point and know exactly where execution is.

## Progress tracking

```markdown
- [x] **Step 1: Initialize project**          <- Done
  - [x] Create project structure
  - [x] Set up configuration

- [ ] **Step 2: Authentication**               <- In Progress
  - [x] Install dependencies
  - [ ] Create auth provider                   <- Currently working
  - [ ] Build login page
```

## Behavior rules

- One phase at a time. Complete it fully before moving to the next.
- Test as you go. If you cannot verify a phase works, do not mark it done.
- No scope creep. New ideas mid-execution go into /create-issue or notes, not the current plan.
- Offer a commit at the end of each phase. Logical checkpoints are easy to revert and easy to reason about.
- Communicate clearly — announce phase starts, report results, ask before continuing if anything is ambiguous.
- When the plan reaches 100%, suggest /document next.
