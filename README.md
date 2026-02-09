# Tech Writer Brag Docs

Streamline brag documentation for technical writers. Generate accomplishment summaries at different cadences using Jira (and optionally GitHub) data.

> **Note:** Atlassian MCP is configured via project `mcp.json`. For GitHub, add it to your global `~/.cursor/mcp.json` (see [Setup](docs/SETUP.md)).

## Cadences

| Cadence   | Use case           | Output style        |
|-----------|--------------------|---------------------|
| **Daily** | Stand-ups, notes   | 3–5 bullets         |
| **Weekly**| 1:1s, team sync    | 5–10 bullets        |
| **Monthly** | Monthly check-ins | Sections + metrics  |
| **Quarter** | Quarterly reviews | Accomplishments + metrics |
| **Semester** | H1/H2 reviews   | Broader summary     |

## Quick start

Open Cursor Chat and ask for a brag doc with the cadence and period:

```
Generate my weekly brag doc for last week.
```

```
Generate my monthly brag doc for February 2026.
```

```
Generate my Q1 2026 brag doc.
```

You can add context not in Jira/GitHub (e.g. presentations, mentoring, one-off wins).

## What you get

One Markdown report per request, saved to `reports/`:

- **Daily:** `brag-daily-YYYY-MM-DD.md`
- **Weekly:** `brag-weekly-YYYY-Www.md`
- **Monthly:** `brag-monthly-YYYY-MM.md`
- **Quarter:** `brag-quarterly-YYYY-Qn.md`
- **Semester:** `brag-semester-YYYY-Hn.md`

## Prerequisites

- Cursor IDE
- Jira Cloud access (Atlassian MCP via `mcp.json`)
- GitHub (optional) for PR/commit data — see [Setup](docs/SETUP.md)

## Project structure

```
tech-writer-brag-docs/
├── .cursorrules          # Assistant behavior and brag-doc templates
├── mcp.json              # Atlassian MCP (project-level)
├── README.md
├── docs/
│   └── SETUP.md          # MCP setup and troubleshooting
├── examples/
│   └── example-request.md
├── context/              # Optional: cadence config
└── reports/              # Generated brag docs
```

## Push to GitHub

1. Create an empty repo on GitHub named `tech-writer-brag-docs`.
2. In this folder run:
   ```bash
   git init
   git remote add origin https://github.com/YOUR_USERNAME/tech-writer-brag-docs.git
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```
