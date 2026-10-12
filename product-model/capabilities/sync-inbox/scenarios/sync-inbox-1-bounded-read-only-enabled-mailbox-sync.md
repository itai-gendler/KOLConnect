---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail"
  },
  "steps": [
    {
      "text": "Request bounded synchronization of selected enabled mailboxes.",
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
      "text": "Enabled selected mailboxes are fetched read-only/peek within initial 30-day/200-message bounds, then synchronized using UID/generation deduplication.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-message",
          "effect": "creates",
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
    },
    {
      "text": "Previously observed identities are deduplicated and only supported observation/match facts are refreshed, preserving mailbox generation provenance.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-message",
          "effect": "changes",
          "facts": [
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

# Bounded read-only enabled-mailbox sync

## Trigger

Request bounded synchronization of selected enabled mailboxes.

## Outcome

Enabled selected mailboxes are fetched read-only/peek within initial 30-day/200-message bounds, then synchronized using UID/generation deduplication.
