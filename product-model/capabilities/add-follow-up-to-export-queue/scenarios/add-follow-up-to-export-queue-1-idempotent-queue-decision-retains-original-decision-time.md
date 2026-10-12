---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail Follow-up"
  },
  "steps": [
    {
      "text": "Request adding the selected correspondent group to the export queue.",
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
      "text": "The selected group enters the export queue; repeated addition retains its original decision timestamp.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-follow-up",
          "effect": "changes",
          "facts": [
            "Export decision time"
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

# Idempotent queue decision retains original decision time

## Trigger

Request adding the selected correspondent group to the export queue.

## Outcome

The selected group enters the export queue; repeated addition retains its original decision timestamp.
