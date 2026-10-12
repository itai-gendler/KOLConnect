---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Choose human approval and supply a review note.",
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
      "text": "The selected submission's human decision becomes Approved with the supplied note.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "content-submission",
          "effect": "changes",
          "facts": [
            "Human review",
            "Review note"
          ],
          "from": "Pending",
          "to": "Approved"
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

# Approved with note

## Trigger

Choose human approval and supply a review note.

## Outcome

The selected submission's human decision becomes Approved with the supplied note.

## Edge cases

- The same decision can replace a prior human decision through this review control; no immutable approval transition is asserted.
