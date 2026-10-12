---
{
  "domain": "campaigns",
  "relations": [
    {
      "entity": "publication-performance-observation",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaign-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/campaign_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/publication.py"
    }
  ]
}
---

# Actual Publication

A recorded actual public publication of a Campaign Creator. Recording does not publish content to the social platform.

## Information kept

- **Publication identity** — Stable normalized publication identity.
- **Cooperation association** — Owning participation.
- **Platform** — Recorded actual social platform.
- **Normalized content URL** — Normalized public content URL.
- **Actual Account** — Actual account association, unknown where omitted.
- **Actual publication time** — Actual publication time, unknown where omitted.
- **Recording time** — Time this actual record was recorded.
- **Observation time** — Time source facts were observed, distinct from actual publication time.
- **Provenance** — Manual or other recorded publication source.
