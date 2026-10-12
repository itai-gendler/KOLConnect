---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail Follow-up"
  },
  "steps": [
    {
      "text": "Request resuming the selected correspondent group.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      }
    },
    {
      "text": "The selected group's stopped timestamp is cleared without changing other decisions.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-follow-up",
          "effect": "changes",
          "facts": [
            "Stopped time"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/mail-follow-up.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up_preferences.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/mail_follow_up_handler.py"
    }
  ]
}
---

# Stop cleared

## Trigger

Request resuming the selected correspondent group.

## Outcome

The selected group's stopped timestamp is cleared without changing other decisions.
