---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "campaign-creator",
      "effect": "reads",
      "facts": [
        "Quote total",
        "Quote currency",
        "Cost",
        "Cost currency"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::workbench"
        },
        {
          "place": "kolconnect-desktop::creator-detail"
        },
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    },
    {
      "type": "entity",
      "id": "campaign",
      "facts": [
        "Budget"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::campaigns"
        },
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    },
    {
      "type": "entity",
      "id": "legacy-cooperation",
      "effect": "reads",
      "facts": [
        "Untyped price"
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
      "target": "app/domain/money.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/performance_analytics.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/campaign_repository.py"
    }
  ]
}
---

# Different currency buckets do not become one scalar total

Original quote/cost amounts remain in currency buckets. Multiple known currencies or known-plus-unknown buckets have no scalar total. An unknown-only compatibility bucket may retain its scalar without acquiring a named currency. Budget and legacy price have no established USD default.
