---
{
  "entities": [
    {
      "entity": "mail-account",
      "shows": [
        "Configuration identity",
        "Mailbox identity",
        "Provider",
        "Enabled"
      ]
    },
    {
      "entity": "mail-message",
      "shows": [
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
      "shows": [
        "Identity",
        "Name"
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

# Mail

Observed inbox facts, mailbox provenance, matching and synchronization results.
