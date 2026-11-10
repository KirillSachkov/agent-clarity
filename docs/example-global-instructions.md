# Example: global instructions

The maintainer's own global instructions, linked for Claude Code (`~/.claude/rules/`), Codex (`~/.codex/AGENTS.md`) and OpenCode (`~/.config/opencode/AGENTS.md`).
The first section does the job of the block from `setup-plain-writing`; the second holds personal working preferences. Take what fits and write your own.

```markdown
# Writing to Kirill

- Reply in Russian, even when the project's language is English. When Kirill writes in another language, reply in that language.
- Before your first reply in a session, open the `plain-writing` skill. Follow it in every text Kirill reads: chat replies, reports, PR descriptions, and issue comments addressed to him.
- Code, commits, and documents for agents follow the project's style; authored content follows the project's writing canon.

## Working with Kirill

- A question about how or why is discussion: answer it and change nothing. A question that asks for an action is a request.
- When he asks «подробнее» or «объясни», explain in full, in text. Draw a diagram with the `explain` skill only when he asks to show or visualize.
- During tool runs, write one line before a multi-step run, one per phase change, and one with the result.
```
