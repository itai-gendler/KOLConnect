---
{
  "kind": "validation",
  "routes": {
    "offered": "Mail Follow-up"
  },
  "steps": [
    {
      "text": "Supply a valid future snooze for the selected correspondent group.",
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
      "text": "An invalid or nonfuture snooze time is refused without changing it.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-follow-up",
          "effect": "reads",
          "facts": [
            "Creator association",
            "Correspondent",
            "Inbound chronology",
            "Outbound chronology",
            "Mail counts",
            "Waiting direction",
            "Waiting age",
            "History confidence",
            "Snooze until",
            "Stopped time",
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

# Nonfuture/invalid time refused

## Trigger

Supply a valid future snooze for the selected correspondent group.

## Outcome

An invalid or nonfuture snooze time is refused without changing it.
