---
description: Audit the vault for orphans, dead links, and contradictions.
---

Lint the `wiki/` vault and report (then offer to fix):

1. **Orphans** — pages not linked from `index.md` or any other page.
2. **Dead links** — `[[wikilinks]]` pointing to pages that don't exist.
3. **Missing links** — pages that mention a known person/concept in prose but
   don't link it.
4. **Stale claims** — pages whose `updated` date is old and whose cited sources
   have changed, or claims with no source at all.
5. **Contradictions** — pages that assert conflicting things; surface both as a
   `> [!contradiction]` callout citing each source.

Present findings as a checklist. Do not delete pages without confirmation.
Refresh `wiki/hot.md` after any fixes.
