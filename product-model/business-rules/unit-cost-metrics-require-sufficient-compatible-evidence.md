---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-campaign-performance",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaign-detail"
        }
      ]
    },
    {
      "type": "entity",
      "id": "campaign-creator",
      "effect": "reads",
      "facts": [
        "Cost",
        "Cost currency"
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
      "target": "app/services/performance_analytics.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/analytics_service.py"
    }
  ]
}
---

# Unit-cost metrics require sufficient compatible evidence

CPV/CPM/CPE require the inspected positive covered denominator and compatible cost buckets. Missing metric evidence does not become zero or an unsupported scalar unit cost.
