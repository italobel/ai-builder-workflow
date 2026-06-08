---
name: explore
description: "Understand a problem fully before writing any code. Reads the codebase, identifies relevant patterns and integration points, surfaces every ambiguity, and asks the user clarifying questions until the scope is clear. Use when the user wants to plan an implementation, understand a codebase before changes, or says things like 'how should we approach this', 'let me think through this', 'analyze this before we start', or '/explore'."
---

# explore

This is the "think before you build" checkpoint. The job is to fully understand the problem and surface every unknown before a single line of code is written.

The non-technical builder failure mode this skill exists to prevent: asking the agent for the whole feature at once, accepting whatever it produces, and discovering halfway through that the original ask was the wrong ask.

## When to use this

- After capturing an issue with /create-issue and now sitting down to actually work on it.
- When the user describes a feature in plain language and wants to start building.
- When the user says "how should we approach", "what would it take to build", or "/explore".
- Before /create-plan. Always.

## What it does

1. Gets the context — pulls the ticket if a project tracker is connected, or asks the user to describe the feature.
2. Analyzes the codebase — finds relevant files, identifies existing patterns, notes integration points.
3. Writes down what is known and what is unknown.
4. Asks the user every clarifying question that comes up, in one consolidated message.
5. Iterates until there are no remaining unknowns.
6. Hands the user a clean scope summary and confirms they are ready for /create-plan.

## How to use it well

The temptation is to assume. Resist it. If a requirement is unclear, ask. If two different technical approaches are possible, list both and ask which one. If something feels out of scope, surface that question rather than silently expanding the work.

A good exploration session usually has two or three rounds of questions. If it has zero, the agent skipped this step. If it has ten, the user is being asked badly — consolidate.

## Question categories to cover

- **Functional:** What exactly should this do? Inputs, outputs, error cases.
- **Scope:** What is in, what is out, are there phases (MVP vs full).
- **Technical:** Any preferred pattern, performance constraints, compatibility requirements.
- **UX (if applicable):** Who is the user, what is the expected flow, any design preferences.
- **Integration:** What existing code does this touch, what depends on it, what might it break.

## Behavior rules

- Do not write code in this step. Not a line.
- Do not assume requirements that were not explicitly stated.
- Group questions by category and number them for easy reference.
- After every round of answers, ask if anything new came up before moving on.
- End the skill by summarizing the scope and suggesting `/create-plan` next.
