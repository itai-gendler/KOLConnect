---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "publication-performance-observation",
      "effect": "reads",
      "facts": [
        "Observation time",
        "Available metrics",
        "Source",
        "Confidence",
        "Refresh provenance"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-detail"
        },
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/publication_performance_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/performance_analytics.py"
    }
  ]
}
---

# Historical observations preserve missing facts and timing

Retained performance history preserves observation timing, source/confidence and unavailable metrics. Metric observation time is distinct from actual publication time.
