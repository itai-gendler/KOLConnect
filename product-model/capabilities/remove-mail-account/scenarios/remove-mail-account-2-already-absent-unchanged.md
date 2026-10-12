---
{
  "kind": "edge",
  "routes": {
    "offered": "Mail Accounts"
  },
  "steps": [
    {
      "text": "Request removing the selected mailbox configuration.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail-accounts"
        }
      }
    },
    {
      "text": "An already-absent configuration remains absent and the operation reports no further change.",
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
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::mail-accounts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/settings_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_auth_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_secret_storage.py"
    }
  ]
}
---

# Already absent unchanged

## Trigger

Request removing the selected mailbox configuration.

## Outcome

An already-absent configuration remains absent and the operation reports no further change.
