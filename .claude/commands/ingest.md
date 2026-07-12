---
description: Ingest one or more sources into linked wiki pages.
argument-hint: [file-or-topic | "all of these"]
---

Ingest sources into the `wiki/` vault. Source(s): $ARGUMENTS
(if empty, process everything in `wiki/.raw/`).

For each source:

1. Read it fully.
2. Extract the key points, the **people/orgs**, and the **concepts**.
3. Create or update:
   - a page in `wiki/sources/` (use `wiki/templates/source.md`),
   - a page per new person in `wiki/people/`,
   - a page per new concept in `wiki/concepts/`.
4. Cross-link everything with `[[wikilinks]]` — link, don't repeat.
5. Add the source to `wiki/index.md` and note contradictions with other pages as
   `> [!contradiction]` callouts citing both sides.
6. Move processed files out of `wiki/.raw/` (or note they were pasted inline).

When ingesting a pile, read them all first, then do a single cross-reference
pass so links between the new pages are complete. Finish by refreshing
`wiki/hot.md`.
