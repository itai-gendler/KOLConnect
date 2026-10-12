---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaigns"
  },
  "steps": [
    {
      "text": "Request setting the activity archive marker.",
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
      "text": "The campaign becomes Archived without replacing its business status.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign",
          "effect": "changes",
          "facts": [
            "Archive time"
          ],
          "from": "Active",
          "to": "Archived"
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

# Mark Archived

## Trigger

Request setting the activity archive marker.

## Outcome

The campaign becomes Archived without replacing its business status.
