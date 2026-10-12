---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaigns"
  },
  "steps": [
    {
      "text": "Request restoring the archived activity.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    },
    {
      "text": "A valid retained business status allows the archived campaign to return Active.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign",
          "effect": "changes",
          "facts": [
            "Archive time"
          ],
          "from": "Archived",
          "to": "Active"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaigns.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/campaign_repository.py"
    }
  ]
}
---

# Valid restore

## Trigger

Request restoring the archived activity.

## Outcome

A valid retained business status allows the archived campaign to return Active.
