---
{
  "domain": "creator-library",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    }
  ]
}
---

# Current Video

A current retained public-content record associated with a Creator, rather than an independently guaranteed all-account inventory.

## Information kept

- **Content identity** — Identity of a current retained content record.
- **Creator association** — Owning canonical profile in current SQLite storage.
- **Content URL** — Recorded public content URL.
- **Available views** — Observed view count, unavailable when absent.
- **Available likes** — Observed like count, unavailable when absent.
- **Available comments** — Observed comment count, unavailable when absent.
- **Capture time** — Time associated with the captured content facts.
