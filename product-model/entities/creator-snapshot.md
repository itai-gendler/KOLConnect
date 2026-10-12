---
{
  "domain": "creator-library",
  "relations": [
    {
      "entity": "video-snapshot",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
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

# Creator Snapshot

A retained creator-account capture that can be addressed in the selected Creator's history; source identity can be upserted.

## Information kept

- **Capture identity** — Capture identity derived from source task and observed account; repeated source identity may upsert.
- **Source task** — Task provenance of the capture.
- **Creator association** — Canonical profile captured.
- **Observed account** — Account provenance where available.
- **Observed metrics** — Available follower/content measurements with observation availability.
- **Score** — Derived creator score when calculable.
- **Level** — Derived insight level, including insufficient evidence.
- **Capture time** — Time of the source capture.
- **Source** — Capture origin.
