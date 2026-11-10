# agent-clarity

Skills that make a coding agent's work easy to understand: clear writing, clear reports.

They are short instructions, not a framework. They follow the Agent Skills format, so they work in Claude Code, Claude Desktop, Codex, OpenCode, Cursor and other agents that read skills.

## Skills

| Skill | What it does |
|---|---|
| [`plain-writing`](skills/plain-writing/SKILL.md) | Every text a person reads, written the way a good colleague explains out loud: result first, brief by default, decisions in one closing block. General rules, plus a Russian file. |
| [`recap`](skills/recap/SKILL.md) | A report of finished work: verdict, what was done, how it was checked, what you must decide. One Markdown text serves as a chat reply, a PR body, a file or a page. |
| [`setup-plain-writing`](skills/setup-plain-writing/SKILL.md) | Run once by hand: adds the short block that makes your agents open `plain-writing` before the first reply. |

[`explain`](skills/in-progress/explain/SKILL.md), pages of diagrams drawn from the code, is in progress; the installer skips it.

## Install

1. Get the skills:

   ```bash
   npx skills add KirillSachkov/agent-clarity
   ```

   Run the same command again to update. In Claude Desktop, upload a skill folder as a zip in the app's skill settings.
   Or clone the repository and link the folders you want into `~/.claude/skills/` (Claude Code) and `~/.agents/skills/` (Codex, OpenCode and others); links keep you on the latest version.
2. Run `/setup-plain-writing`, or paste [the block](skills/setup-plain-writing/block.md) into your agent's global instructions yourself. Without the block, agents open `plain-writing` only when its description matches.

`recap` uses `gh` to write a PR body. Its pages load Mermaid from cdn.jsdelivr.net; without the network, diagrams stay as text.

## Make it yours

The rules are defaults. Your global or project instructions win over them, so change the style there, not in the skill files that an update replaces:
add a line to the block, for example «Пиши без таблиц» or "Use no emoji".

For another language, the general rules work alone. To add its words and punctuation, add `skills/plain-writing/references/<lang>.md` in a fork or send a PR.

The skills use what your app offers: a question dialog with options when the app has one, links in the form the app makes clickable, pages shown inside the chat where the app can show them.

## How they fit together

- `plain-writing` decides how text reads. Your global instructions tell the agent to open it before the first reply.
- `recap` decides what a report holds and where it goes; its prose comes from `plain-writing`. Your pipeline decides when to write one: on request, in the PR step, or at acceptance.

## По-русски

Скиллы, чтобы работу агента было легко понять. `plain-writing` учит агента писать понятно: сначала результат, коротко, слова как в речи разработчиков, все вопросы к вам в одном блоке в конце. Для русского есть отдельный файл правил. `recap` пишет отчёт о сделанной работе: в чат, в описание PR, в файл или страницей. Установка выше, после неё запустите `/setup-plain-writing`. Стиль меняется строкой в своих инструкциях агента, см. «Make it yours».

## Contributing

Open an issue or a PR. `python3 scripts/check.py` must print OK; CI runs it on every PR.

## License

MIT
