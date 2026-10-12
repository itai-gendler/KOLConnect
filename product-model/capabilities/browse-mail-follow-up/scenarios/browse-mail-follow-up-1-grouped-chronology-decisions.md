---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail Follow-up"
  },
  "steps": [
    {
      "text": "Request grouped correspondence chronology and follow-up decisions.",
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
      "text": "Correspondent groups disclose bounded inbound/outbound chronology, waiting direction and independent saved decisions.",
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
        },
        {
          "entity": "creator-account",
          "effect": "reads",
          "facts": [
            "Canonical identity",
            "Platform",
            "Profile identity",
            "Username",
            "Creator association",
            "Account email",
            "Followers",
            "Latest post",
            "Capture status",
            "Capture time",
            "Source",
            "Notes"
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

# Grouped chronology/decisions

## Trigger

Request grouped correspondence chronology and follow-up decisions.

## Outcome

Correspondent groups disclose bounded inbound/outbound chronology, waiting direction and independent saved decisions.
