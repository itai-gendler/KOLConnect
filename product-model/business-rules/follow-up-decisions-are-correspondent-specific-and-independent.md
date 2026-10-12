---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "snooze-mail-follow-up",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      ]
    },
    {
      "type": "capability",
      "id": "clear-mail-follow-up-snooze",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      ]
    },
    {
      "type": "capability",
      "id": "stop-mail-follow-up",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      ]
    },
    {
      "type": "capability",
      "id": "resume-mail-follow-up",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-follow-up-to-export-queue",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-follow-up-from-export-queue",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail-follow-up"
        }
      ]
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

# Follow-up decisions are correspondent-specific and independent

Snooze, stopped and export-decision timestamps belong to a canonical Creator/correspondent pair and remain independent. Repeated export addition preserves its original decision time.
