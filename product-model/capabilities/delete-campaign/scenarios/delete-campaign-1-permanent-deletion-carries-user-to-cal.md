---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Request permanent deletion of the selected activity.",
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
      "text": "The selected campaign and supported participation/brief/submission/publication dependents are permanently removed; the user is carried to inventory.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "campaign-creator",
          "effect": "removes",
          "with": "campaign",
          "from": "Active"
        },
        {
          "entity": "campaign-brief",
          "effect": "removes",
          "with": "campaign"
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

# Permanent deletion carries user to CAL

## Trigger

Request permanent deletion of the selected activity.

## Outcome

The selected campaign and supported participation/brief/submission/publication dependents are permanently removed; the user is carried to inventory.


## Edge cases

- This case removes Active campaign/participation records and Pending submissions. Archive markers and a different human-review state do not by themselves prevent the same permanent removal.
