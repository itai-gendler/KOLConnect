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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/schema.py"
    }
  ]
}
---

# Video Snapshot

One retained content observation within a Creator Snapshot.

## Information kept

- **Observation identity** — Identity of this content observation.
- **Creator association** — Canonical profile owning this observation, retained independently of its snapshot identity.
- **Snapshot association** — Containing creator capture.
- **Content identity** — Identity of observed content.
- **Content URL** — Observed public content URL.
- **Platform** — Observed platform.
- **Available metrics** — Available observed views, likes and comments, without fabricated zeroes.
- **Capture time** — Time of observation.
