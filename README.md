# wren-engine-skills

AI agent skills for the [Wren Engine CLI](https://github.com/Canner/wren-engine) (`wren`). Teach your AI agent how to query data, generate MDL projects, and manage semantic layers across 22+ data sources.

## Installation

### npx skills (recommended)

Install all skills into your agent of choice:

```bash
npx skills add goldmedal/wren-engine-skills --skill '*' --agent claude-code
```

Install a specific skill:

```bash
npx skills add goldmedal/wren-engine-skills --skill wren-usage --agent claude-code
```

Replace `--agent claude-code` with your agent: `cursor`, `windsurf`, `copilot`, etc.

### Manual copy (Claude Code)

```bash
cp -r skills/wren-usage skills/wren-generate-mdl ~/.claude/skills/
```

## Available Skills

| Skill | Description |
|-------|-------------|
| [wren-usage](skills/wren-usage/SKILL.md) | **Primary skill** - CLI workflow guide: query data via `wren --sql`, gather schema context with `wren memory`, store/recall queries, handle errors |
| [wren-generate-mdl](skills/wren-generate-mdl/SKILL.md) | Generate a Wren MDL project from a live database - schema discovery, type normalization, YAML generation |

### wren-usage reference files

| File | Topic |
|------|-------|
| [references/memory.md](skills/wren-usage/references/memory.md) | When to index, fetch, store, and recall |
| [references/wren-sql.md](skills/wren-usage/references/wren-sql.md) | CTE rewrite pipeline, SQL rules, error diagnosis |

## Updating

```bash
npx skills add goldmedal/wren-engine-skills --skill '*' --agent claude-code --force
```

## Requirements

- `wren` CLI installed (`pip install 'wren-engine[ui,memory]'` or `pip install 'wren-engine[ui,memory,<datasource>]'` for specific database drivers)
- A database connection (configured via `wren profile add`)
- An AI client that supports skills (Claude Code, Cursor, Windsurf, etc.)

## License

Apache-2.0
