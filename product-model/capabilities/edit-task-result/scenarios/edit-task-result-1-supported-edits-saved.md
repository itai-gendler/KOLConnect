---
{
  "kind": "primary",
  "routes": {
    "offered": "Review Results"
  },
  "steps": [
    {
      "text": "Supply supported confirmed-field edits for the selected result.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    },
    {
      "text": "Supported email, follower, WhatsApp and note edits are saved; eligible already-imported canonical facts synchronize afterwards.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
            "Confirmed edits"
          ]
        },
        {
          "entity": "creator",
          "effect": "changes",
          "facts": [
            "Contact details",
            "Notes",
            "Update time"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "changes",
          "facts": [
            "Account email",
            "Followers"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::review-results"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_result_mapper.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    }
  ]
}
---

# Supported edits saved

## Trigger

Supply supported confirmed-field edits for the selected result.

## Outcome

Supported email, follower, WhatsApp and note edits are saved; eligible already-imported canonical facts are synchronized.
