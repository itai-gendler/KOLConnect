---
{
  "kind": "primary",
  "routes": {
    "offered": "Chrome Accounts"
  },
  "steps": [
    {
      "text": "Request discovered browser-profile availability and saved configuration.",
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
      "text": "Discovered browser profiles disclose availability and current saved aliases/notes.",
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

# Discovered profiles and saved configuration

## Trigger

Request discovered browser-profile availability and saved configuration.

## Outcome

Discovered browser profiles disclose availability and current saved aliases/notes.
