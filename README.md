# AI Builder Workflow

Five skills I use to build with AI as a non-technical leader. The discipline that turns AI from a toy into a tool.

## The workflow

The order matters more than any individual prompt.

1. `/create-issue` — capture a bug or idea without breaking flow
2. `/explore` — think before you build
3. `/create-plan` — break work into phases, not one-shots
4. `/execute` — work the plan one phase at a time
5. `/document` — read the actual code and write the truth

## Why this exists

I have been showing this workflow to other CS leaders, founders, and friends on coaching calls. The feedback has been consistent enough that I put the markdown files in one place so people can download them, drop them into their own setup, and start.

The lesson behind every one of these commands is the same one: the skill is not the prompt. It is the patience to break work down to a size the agent can actually finish.

## How to install

These are Claude Code skills. Drop the `skills/` folder into your Claude Code skills directory (typically `~/.claude/skills/` or your project's `.claude/skills/`). Restart Claude Code or reload skills, and they will be available as slash commands.

If you are not using Claude Code, the markdown files still work as standalone prompts — paste the body of any `SKILL.md` into your AI tool of choice when you want that step of the workflow.

## Suggested use

- Start with `/create-issue` whenever an idea or bug interrupts your current work. Keep it on the shelf.
- When you sit down to build, run `/explore` first. Resist the urge to skip it.
- Use `/create-plan` to turn the exploration into a phased plan — three to five phases, each testable on its own.
- Run `/execute` one phase at a time. Test. Commit. Repeat.
- Finish with `/document`. Future-you will thank present-you.

## Credit

These skills are inspired by Claude Code's example skills bundle. The workflow opinion, ordering, and coaching framing are mine, shaped by months of building internal tools at Ringover as a non-technical leader and showing the workflow to others.

## License

MIT. See [LICENSE](LICENSE).

## Connect

If you try this workflow and want to compare notes — what worked, what did not, what you would change — my DMs are open on [LinkedIn](https://www.linkedin.com/in/italobelandria/).
