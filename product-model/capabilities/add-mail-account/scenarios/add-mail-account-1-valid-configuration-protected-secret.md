---
{
  "kind": "primary",
  "routes": {
    "offered": "Mail Accounts"
  },
  "steps": [
    {
      "text": "Supply valid mailbox endpoints, identities and secret.",
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
      "text": "A valid mailbox configuration is created with the secret protected by the native facility.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "mail-account",
          "effect": "creates",
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

# Valid configuration/protected secret

## Trigger

Supply valid mailbox endpoints, identities and secret.

## Outcome

A valid mailbox configuration is created with the secret protected by the native facility.
