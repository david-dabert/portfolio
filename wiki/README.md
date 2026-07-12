# The Vault

A plain-Markdown knowledge base — your "second brain." Every note is a file you
own; there is no database and no lock-in. See [`../WIKI.md`](../WIKI.md) for the
full operating protocol an AI agent follows when reading and writing here.

## Layout

- **[`index.md`](./index.md)** — master index; the map of everything.
- **[`hot.md`](./hot.md)** — recent-context cache; read this first.
- **[`.raw/`](./.raw/)** — inbox for raw sources awaiting ingest.
- **[`templates/`](./templates/)** — starting points for new pages.
- **[`concepts/`](./concepts/)** — ideas, patterns, definitions.
- **[`people/`](./people/)** — people and organizations.
- **[`sources/`](./sources/)** — one page per ingested source, with citations.
- **[`notes/`](./notes/)** — free-form notes and saved conversations.

## Quick start

1. Drop a source into `.raw/` (or paste it into a chat).
2. Run `/ingest` — pages get created and cross-linked.
3. Ask "what do you know about X?" — answers cite the pages they came from.
4. Run `/lint` weekly to catch orphans, dead links, and contradictions.

## Conventions

- Cross-link with `[[Page Title]]` wikilinks.
- Start each page with YAML frontmatter (see the templates).
- One idea/person/source per page — keep pages atomic.
- Anything derived from a source links back to that source's page.
