# WIKI — Operating Protocol

This file tells any AI agent (Claude Code, etc.) how to read from and write to
the knowledge vault that lives in [`wiki/`](./wiki/). It is a self-contained,
plain-Markdown "second brain" inspired by Andrej Karpathy's LLM Wiki pattern.
Everything is files on disk that you own — no database, no lock-in.

> [!note] Scope
> This scaffold is content-only. It does **not** install plugins, clone
> external repositories, or register MCP servers. Those are optional and left
> to you. See [Optional integrations](#optional-integrations) below.

## Reading order (always follow this)

When you need context that is not already in the current conversation:

1. Read [`wiki/hot.md`](./wiki/hot.md) first — the recent-context cache.
2. If that is not enough, read [`wiki/index.md`](./wiki/index.md) — the master index.
3. For domain detail, read the relevant sub-index under `wiki/` (e.g. a domain's `_index.md`).
4. Only then drill into specific pages under `wiki/concepts/`, `wiki/people/`, `wiki/sources/`, `wiki/notes/`.

Do **not** read the wiki for general coding questions unrelated to its contents.

## Vault structure

```
wiki/
├── README.md          How the vault is organized (human-facing)
├── index.md           Master index — links out to everything
├── hot.md             Recent-context cache, refreshed at end of session
├── .raw/              Inbox: drop raw sources here to be ingested
├── templates/         Page templates (source / concept / person)
├── concepts/          Ideas, patterns, definitions
├── people/            People, orgs, authors
├── sources/           One page per ingested source (paper, article, video…)
└── notes/             Free-form notes, saved conversations, decisions
```

## Conventions

- **Wikilinks:** use `[[Page Title]]` to cross-link. Prefer linking over repeating.
- **Frontmatter:** every page starts with YAML frontmatter (`type`, `tags`, `created`, `updated`, `aliases`).
- **Callouts:** use Obsidian callouts for signal — `> [!contradiction]`, `> [!question]`, `> [!summary]`.
- **Atomic pages:** one idea/person/source per page. Split rather than nest.
- **Cite sources:** claims that come from a source link back to its `sources/` page.

## The workflow (slash commands)

These are defined as plain Markdown command files in [`.claude/commands/`](./.claude/commands/):

| Command | What it does |
|---|---|
| `/wiki` | Check the vault, ask what it's for, scaffold/repair structure. |
| `/ingest` | Read a source (or a pile), extract entities, cross-link, file pages. |
| `/save` | Turn the current conversation into a permanent note. |
| `/autoresearch` | Run multi-round web research, then file the findings. |
| `/lint` | Find orphans, dead links, stale claims, missing links. |
| `/think` | Run a structured multi-stage reasoning loop before a hard decision. |

You can also just ask in natural language ("ingest this", "what do you know about X?", "lint the wiki").

## End-of-session cache refresh

Before ending a working session, update [`wiki/hot.md`](./wiki/hot.md) with the
most recent context so the next session opens warm: what changed, open threads,
and pointers into the vault. Keep it short (it is a cache, not an archive).

## Use across projects

Point other projects at this vault by adding to their `CLAUDE.md`:

```md
## Wiki Knowledge Base
Path: <path-to-this-repo>/wiki

When you need context not already in this project:
1. Read wiki/hot.md first (recent context cache)
2. If not enough, read wiki/index.md
3. If you need domain details, read the relevant sub-index
4. Only then drill into specific wiki pages

Do NOT read the wiki for general coding questions.
```

## Optional integrations

None of these are required; the vault works as plain files without them.

- **Obsidian:** open this repo folder as a vault (Manage Vaults → Open folder as vault).
- **MCP filesystem access:** lets an agent read/write notes directly instead of pasting.
- **Obsidian Git:** auto-commit the vault on a timer for full undo history.
- **Web Clipper:** send articles into `wiki/.raw/` for later ingest.

Verify third-party tools and repositories yourself before installing them.
