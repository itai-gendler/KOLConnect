---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail Follow-up"
  },
  "steps": [
    {
      "text": "Request clearing the selected correspondent group's snooze.",
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
      "text": "The selected group's snooze is cleared; stop and export decisions remain unchanged.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-follow-up",
          "effect": "changes",
          "facts": [
            "Snooze until"
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

# Clear

## Trigger

Request clearing the selected correspondent group's snooze.

## Outcome

The selected group's snooze is cleared; stop and export decisions remain unchanged.
