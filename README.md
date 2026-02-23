# Tech Writer Brag Docs

Streamline brag documentation for technical writers. Generate accomplishment summaries at different cadences using Jira (and optionally GitHub) data.

> **Note:** Atlassian MCP is configured via project `mcp.json`. For GitHub, add it to your global `~/.cursor/mcp.json` (see [Setup](docs/SETUP.md)).

## Cadences

| Cadence   | Use case           | Output style        |
|-----------|--------------------|---------------------|
| **Daily** | Stand-ups, notes   | 3–5 bullets         |
| **Weekly**| 1:1s, team sync    | 5–10 bullets        |
| **Biweekly**| Two-week sprint reviews | 5–10 bullets with sections |
| **Monthly** | Monthly check-ins | Sections + metrics  |
| **Quarter** | Quarterly reviews | Accomplishments + metrics |
| **Semester** | H1/H2 reviews   | Broader summary     |

## Quick start

### Option 1: @brag Command (fastest)

Open Cursor Chat (Ctrl+L / Cmd+L) and use the `@brag` command:

```
@brag daily yesterday
```

```
@brag weekly last week
```

```
@brag biweekly last 2 weeks
```

```
@brag monthly February 2026
```

```
@brag quarter Q1 2026
```

```
@brag semester H1 2026
```

Add context on new lines:

```
@brag weekly last week
Also include:
- Presented at team sync
- Mentored new hire
```

### Option 2: Natural language

Ask in Cursor Chat:

```
Generate my weekly brag doc for last week.
```

```
Generate my monthly brag doc for February 2026.
```

## What you get

One Markdown report per request, saved to `reports/`:

- **Daily:** `brag-daily-YYYY-MM-DD.md`
- **Weekly:** `brag-weekly-YYYY-Www.md`
- **Biweekly:** `brag-biweekly-YYYY-MM-DD-to-YYYY-MM-DD.md`
- **Monthly:** `brag-monthly-YYYY-MM.md`
- **Quarter:** `brag-quarter-YYYY-Qn.md`
- **Semester:** `brag-semester-YYYY-Hn.md`

## Prerequisites

- Cursor IDE
- Jira Cloud access (Atlassian MCP via `mcp.json`)
- GitHub (optional) for PR/commit data — see [Setup](docs/SETUP.md)

## Project structure

```
tech-writer-brag-docs/
├── .cursor/
│   └── commands/
│       └── brag.md       # @brag command definition
├── .cursorrules          # Assistant behavior and templates
├── mcp.json              # Atlassian MCP (project-level)
├── docs/
│   └── SETUP.md          # MCP setup and troubleshooting
├── examples/
│   └── example-request.md
└── reports/              # Generated brag docs
```
