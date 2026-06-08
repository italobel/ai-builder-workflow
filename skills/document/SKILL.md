---
name: document
description: "After code changes ship, read the actual implementation and update documentation to match — README, changelog, code comments, and any internal docs that explain how the new piece connects to the existing system. Use when the user finishes a feature, runs a deploy, or says things like 'update the docs', 'sync the readme', 'document what we built', or '/document'."
---

# document

The goal is to bring documentation in line with what the code actually does. Not what was planned. Not what the user thinks happened. What is in the code, right now.

This step is the one most easily skipped and the one that pays back the most over time. Future-you will not remember the decisions present-you made. The doc is the only thing that will.

## When to use this

- A feature has just shipped or been merged.
- A deploy is complete and the new behavior is live.
- The user says "update the docs", "document this", "sync the changelog", or "/document".
- Anytime code changes substantially diverge from what the docs claim.

## Critical rule

Do not trust the existing documentation. Read the code. Documentation that has not been touched in months will confidently lie to you about how the system works.

## What it does

1. Identifies what changed — uses `git diff` against the previous commit, or asks the user, or reviews the just-completed plan file.
2. Reads the actual changed code, file by file.
3. Determines which docs need updating based on the type of change:
   - New feature → README, changelog, API docs
   - Bug fix → changelog
   - Breaking change → README, changelog, migration guide
   - New endpoint → API docs, possibly README
   - Config change → README, `.env.example`
   - Internal refactor → changelog (if notable), code comments
4. Updates each affected file.
5. Verifies the docs now match the code.

## Documentation style

Do:
- Write in plain language a future teammate would understand.
- Keep it concise. Two lines that are right beat ten lines that are vague.
- Document what is, not what might be.
- Use examples that work — try them if you have any doubt.

Don't:
- Use enterprise filler ("leveraging synergies", "robust solution", "seamless integration").
- Document assumptions you have not verified.
- Copy-paste from old docs without re-reading the code.

## Changelog entry format

```markdown
## [Unreleased]

### Added
- {User-facing description of the new feature}

### Changed
- {Description of behavior changes}

### Fixed
- {Bug fix in plain language}
```

## Behavior rules

- Read the code first, every time. No exceptions.
- Update only what is affected by the changes. Do not rewrite untouched sections.
- Match the project's existing documentation style and structure.
- If something is ambiguous, ask the user about intent rather than guessing.
- Offer to commit the doc changes when finished.
