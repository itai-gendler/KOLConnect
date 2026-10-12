---
{
  "domain": "creator-library",
  "relations": [
    {
      "entity": "creator-snapshot",
      "verb": "identifies",
      "cardinality": "one-to-many"
    },
    {
      "entity": "actual-publication",
      "verb": "identifies",
      "cardinality": "one-to-many"
    },
    {
      "entity": "content-submission",
      "verb": "is-referenced-by",
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

# Creator Account

One canonical social-platform identity exclusively associated with one Creator.

## Information kept

- **Canonical identity** — Normalized platform-account identity used for lookup and collision detection.
- **Platform** — TikTok, Instagram or YouTube platform of this account.
- **Profile identity** — Normalized platform profile address and available platform identity.
- **Username** — Observed account handle.
- **Creator association** — Exclusive canonical profile association.
- **Account email** — Account-level contact email, with conflicting observations preserved rather than overwritten.
- **Followers** — Observed follower measurement, unavailable when not observed.
- **Latest post** — Latest observed post date.
- **Capture status** — Recorded capture status independent of human review.
- **Capture time** — Time of capture observation.
- **Source** — Capture source and task provenance where available.
- **Notes** — Account notes protected during extension refresh.
