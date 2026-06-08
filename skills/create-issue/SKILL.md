---
name: create-issue
description: "Capture a bug, feature idea, or improvement into a project tracker (Linear, Jira, or similar) in under a minute without breaking the flow of your current work. Use when the user is mid-task and a separate thought interrupts them — phrases like 'log this', 'we should track that', 'create a ticket for', 'add to the backlog', or '/create-issue'."
---

# create-issue

The goal is to capture a thought fast and get the user back to what they were doing. Two minutes total, max. The thought is the asset. Losing it is the cost.

## When to use this

- User is mid-development and notices a bug elsewhere.
- User has a feature idea while doing something unrelated.
- User says "I should track this" or "add to the backlog" or "/create-issue".
- A separate concern surfaces in conversation and would otherwise be forgotten.

## What it does

1. Asks the user a small number of targeted questions to fill in gaps — what is the issue, what does the current behavior look like, what is the expected outcome.
2. Writes a short, structured ticket description.
3. Creates the issue in the connected project tracker (Linear, Jira, or whichever MCP is wired up).
4. Hands the user back the issue link and lets them return to what they were doing.

## How to use it well

The trap is making this step too long. If the conversation to capture an issue takes more time than just doing the thing, the user will stop using the skill and start mentally hoarding tickets, which is what we are trying to fix in the first place.

Default behavior:
- Ask at most two or three questions in a single message.
- Skip context-gathering if the issue is obvious.
- Use sensible defaults for priority and type unless the user signals otherwise.
- Confirm once, then create.

## Issue body format

```markdown
### TL;DR
{One-sentence summary}

### Current state
{What is happening today}

### Expected outcome
{What should happen instead}

### Relevant files (optional, max 3)
- `{path}` — {why it matters}

### Notes / risks
{Anything worth flagging}
```

## Behavior rules

- Do not over-ask. Two or three targeted questions, not a form.
- Default priority is "normal/medium" unless the user signals urgency.
- If the tracker requires a team or project and it is not clear, list options and let the user pick once.
- After creation, return the issue link in one short line. Do not write a closing essay.
