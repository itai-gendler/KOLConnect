---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Request removing the selected actual record.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaign-detail"
        }
      }
    },
    {
      "text": "The actual record is removed and remaining compatibility publication facts rebuilt.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "actual-publication",
          "effect": "removes"
        },
        {
          "entity": "campaign-creator",
          "effect": "changes",
          "facts": [
            "Compatibility publication facts"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaign-detail"
        }
      }
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
      "target": "app/repositories/publication_performance_repository.py"
    }
  ]
}
---

# Actual record removed

## Trigger

Request removing the selected actual record.

## Outcome

The actual record is removed and remaining compatibility publication facts rebuilt.
