---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sync-inbox",
      "contexts": [
        {
          "place": "kolconnect-desktop::mail"
        }
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

# Inbox observation is bounded and read-only

Inbox fetch is read-only/peek. Initial history is bounded to thirty days and two hundred messages per mailbox, followed by UID/generation deduplication. Successful accounts survive failures of other accounts.
