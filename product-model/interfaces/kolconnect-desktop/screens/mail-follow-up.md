---
{
  "entities": [
    {
      "entity": "mail-follow-up",
      "shows": [
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
      ],
      "collects": [
        "Snooze until",
        "Stopped time",
        "Export decision time"
      ]
    },
    {
      "entity": "mail-message",
      "shows": [
        "Addresses",
        "Subject",
        "Message time",
        "Observation time",
        "Direction",
        "Match evidence"
      ]
    },
    {
      "entity": "creator",
      "shows": [
        "Identity",
        "Name",
        "Contact details",
        "Business status"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Account email",
        "Creator association"
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

# Mail Follow-up

Creator/correspondent groups, bounded chronology, uncertainty and snooze/stop/export decisions.
