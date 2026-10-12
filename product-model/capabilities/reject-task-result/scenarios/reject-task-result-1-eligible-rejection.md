---
{
  "kind": "primary",
  "routes": {
    "offered": "Review Results"
  },
  "steps": [
    {
      "text": "Request rejection of the selected result with an optional reason.",
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
      "text": "An eligible unapproved result becomes Rejected with the supplied optional reason.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "task-result",
          "effect": "changes",
          "facts": [
            "Review decision",
            "Review reason",
            "Review time"
          ],
          "from": "Pending",
          "to": "Rejected"
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

# Eligible rejection

## Trigger

Request rejection of the selected result with an optional reason.

## Outcome

An eligible unapproved result becomes Rejected with the supplied optional reason.
