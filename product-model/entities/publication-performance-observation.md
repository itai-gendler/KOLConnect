---
{
  "domain": "campaigns",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/publication_performance_repository.py#_record"
    }
  ]
}
---

# Publication Performance Observation

An individually retained performance observation of an Actual Publication. Production refresh currently returns unavailable or deferred rather than creating a successful observation.

## Information kept

- **Observation identity** — Identity of a retained metric observation.
- **Publication association** — Publication observed.
- **Observation time** — Time of the metric observation.
- **Available metrics** — Available views, likes, comments and shares where retained.
- **Engagement** — Derived engagement where supported by available evidence.
- **Source** — Recorded observation source.
- **Confidence** — Recorded observation confidence.
- **Refresh provenance** — Provider and refresh provenance of retained facts.
