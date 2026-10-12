---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail"
  },
  "steps": [
    {
      "text": "Request observed inbox and match/synchronization facts.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail"
        }
      }
    },
    {
      "text": "Observed inbox facts include historical mailbox identity, matching evidence and CRM synchronization results.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-account",
          "effect": "reads",
          "facts": [
            "Configuration identity",
            "Mailbox identity",
            "Provider",
            "Connection endpoints",
            "Usernames",
            "Sender details",
            "Enabled",
            "Protected credentials"
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
          "place": "kolconnect-desktop::mail"
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
      "target": "app/mail_sync.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_inbox_facts.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/settings_handler.py"
    }
  ]
}
---

# Observed inbox/matching/sync facts

## Trigger

Request observed inbox and match/synchronization facts.

## Outcome

Observed inbox facts include historical mailbox identity, matching evidence and CRM synchronization results.
