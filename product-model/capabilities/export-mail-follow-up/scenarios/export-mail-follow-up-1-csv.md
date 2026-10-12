---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail Follow-up"
  },
  "steps": [
    {
      "text": "Choose CSV or XLSX download of queued correspondence groups.",
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
      "text": "Queued follow-up facts are downloaded as CSV.",
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
        },
        {
          "entity": "mail-message",
          "effect": "reads",
          "facts": [
            "Observed message identity",
            "Historical mailbox identity",
            "Mailbox generation",
            "Addresses",
            "Subject",
            "Message time",
            "Observation time",
            "Available content",
            "Direction",
            "Match evidence",
            "CRM-sync outcome"
          ]
        },
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Tags",
            "Notes",
            "Descriptive owner",
            "Agency association",
            "Contact association",
            "Business status",
            "Archive time",
            "Update time",
            "Linked review task"
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

# CSV

## Trigger

Choose CSV or XLSX download of queued correspondence groups.

## Outcome

Queued follow-up facts are downloaded as CSV.
