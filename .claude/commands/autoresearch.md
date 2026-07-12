---
description: Run multi-round web research on a topic and file the findings.
argument-hint: <topic>
---

Autonomously research: $ARGUMENTS

Run up to 3 rounds of: search → fetch promising sources → note what's still
missing → search again. Then:

1. File each substantial source as a page in `wiki/sources/` (cite the URL).
2. Create/update `concepts/` and `people/` pages for what you found.
3. Write a synthesis note in `wiki/notes/` that answers the topic and links its
   supporting sources.
4. Flag disagreements between sources as `> [!contradiction]` callouts.
5. Update `wiki/index.md` and `wiki/hot.md`.

Only assert what a fetched source supports; cite everything. If a claim can't be
verified, say so rather than filing it as fact.
