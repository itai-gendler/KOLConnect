---
{
  "kind": "primary",
  "routes": {
    "offered": "Chrome Accounts"
  },
  "steps": [
    {
      "text": "Request removing saved browser configuration.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::chrome-accounts"
        }
      }
    },
    {
      "text": "The saved configuration is removed while its operating-system browser profile remains.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "chrome-account-configuration",
          "effect": "removes"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::chrome-accounts"
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
    }
  ]
}
---

# Configuration removed

## Trigger

Request removing saved browser configuration.

## Outcome

The saved configuration is removed while its operating-system browser profile remains.
