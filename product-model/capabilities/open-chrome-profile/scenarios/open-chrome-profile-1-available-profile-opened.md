---
{
  "kind": "primary",
  "routes": {
    "offered": "Chrome Accounts"
  },
  "steps": [
    {
      "text": "Request opening an available discovered browser profile.",
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
      "text": "The available discovered browser profile is opened.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "chrome-account-configuration",
          "effect": "reads",
          "facts": [
            "Discovered profile identity",
            "Availability",
            "Alias",
            "Notes"
          ]
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

# Available profile opened

## Trigger

Request opening an available discovered browser profile.

## Outcome

The available discovered browser profile is opened.
