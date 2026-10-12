---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "creator-account",
      "effect": "reads",
      "facts": [
        "Followers",
        "Latest post"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-detail"
        }
      ]
    },
    {
      "type": "entity",
      "id": "creator-snapshot",
      "effect": "reads",
      "facts": [
        "Observed account",
        "Observed metrics"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::creator-detail"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_intelligence_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    }
  ]
}
---

# Selected-account metrics are not all-account totals

Account-selected metrics and latest observed capture evidence describe their selected scope; they do not establish an aggregation across every account of the canonical Creator.
