---
{
  "kind": "validation",
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
      "text": "Invalid settings or native secret-protection failure prevents saving the configuration.",
      "kind": "product",
      "actor": "local-user",
      "entities": [],
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

# Invalid/native-protection failure refused

## Trigger

Supply valid mailbox endpoints, identities and secret.

## Outcome

Invalid settings or native secret-protection failure prevents saving the configuration.
