# Second brain skills

Two [Claude Code](https://docs.claude.com/en/docs/claude-code) skills for anyone who keeps a second
brain in Obsidian, plain markdown or a repo that Claude works in.

| Skill | What it does |
|---|---|
| `brain-audit` | Scores a second brain 0-10 on six areas (capture, structure, links, freshness, instructions, outcomes) and writes a report with ranked fixes and quick wins. |
| `arch-review` | Reviews its architecture: folders, data flow, generated vs hand-written files, docs vs reality, dead weight, and how much context a fresh AI session has to load. Ends with ranked recommendations. |

Both are read-only. They change nothing in the brain they look at and write the report beside it.
They need no setup beyond shell tools (`find`, `grep`, `wc`, `git`).

## Install

Copy the folders into your skills directory, either for one project or for all of them:

```
cp -r .claude/skills/brain-audit .claude/skills/arch-review ~/.claude/skills/
```

## Use

In Claude Code, ask in plain words or name the skill:

```
Audit my second brain at ~/Obsidian/Vault
```

```
Run an architecture review of this repo
```

## Licence

MIT.
