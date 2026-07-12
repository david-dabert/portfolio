---
description: Save the current conversation as a permanent vault note.
argument-hint: [optional title]
---

Turn the current conversation into a permanent note in `wiki/notes/`.

1. Summarize the conversation into an atomic note (title: $ARGUMENTS if given,
   otherwise derive one).
2. Use YAML frontmatter (`type: note`, tags, dates).
3. Cross-link people/concepts mentioned to their `wiki/` pages; create stubs if
   they don't exist yet.
4. Add the note to `wiki/index.md` under Notes and refresh `wiki/hot.md`.

Keep it faithful to what was actually discussed — do not invent conclusions.
