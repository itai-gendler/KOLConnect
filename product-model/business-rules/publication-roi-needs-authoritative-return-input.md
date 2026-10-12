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

# Publication ROI needs authoritative return input

Publication ROI is unavailable without authoritative return/revenue input. A retained manually recorded cooperation ROI does not supply that missing publication return.
