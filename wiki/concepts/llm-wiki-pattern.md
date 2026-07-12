---
type: concept
tags: [concept, knowledge-management, ai]
created: 2026-07-12
updated: 2026-07-12
aliases: [LLM Wiki, LLM Wiki Pattern]
---

# LLM Wiki Pattern

> [!summary] In one line
> Store knowledge as a graph of plain-Markdown pages that an LLM both writes and
> reads, so context compounds instead of scattering.

## What it is

A knowledge base kept as many small, cross-linked Markdown files. An agent
ingests sources into atomic pages, links them with wikilinks, and later answers
questions by walking the graph — index first, then pages — citing what it read.
Because everything is files on disk, you own the data and can open it in any
editor (e.g. Obsidian).

## Why it matters

- **Compounding:** each source enriches the graph; retrieval improves over time.
- **Ownership:** plain files, no database, no lock-in.
- **Agent-friendly:** the same structure an LLM writes is the one it reads back.

## Related

- [[second-brain]]
- Originated by [[andrej-karpathy]].

## Sources

- [[example-source]] — replace with the primary write-up once ingested.
