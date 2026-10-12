---
{
  "kind": "primary",
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
      "text": "The configuration is removed while observed messages retain historical mailbox provenance.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-account",
          "effect": "removes"
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

# Configuration removed, observed messages retained

## Trigger

Request removing the selected mailbox configuration.

## Outcome

The configuration is removed while observed messages retain historical mailbox provenance.
