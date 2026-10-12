---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Request removing the selected participation.",
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
      "text": "The participation and supported submissions/publications are removed without asserting observation-history cleanup.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign-creator",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "content-submission",
          "effect": "removes",
          "with": "campaign-creator",
          "from": "Pending"
        },
        {
          "entity": "actual-publication",
          "effect": "removes",
          "with": "campaign-creator"
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
    }
  ]
}
---

# Participation and supported dependents removed

## Trigger

Request removing the selected participation.

## Outcome

The participation and supported submissions/publications are removed without asserting observation-history cleanup.


## Edge cases

- This case removes Active campaign/participation records and Pending submissions. Archive markers and a different human-review state do not by themselves prevent the same permanent removal.
