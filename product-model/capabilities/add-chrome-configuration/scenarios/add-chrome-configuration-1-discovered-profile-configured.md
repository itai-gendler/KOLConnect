---
{
  "kind": "primary",
  "routes": {
    "offered": "Chrome Accounts"
  },
  "steps": [
    {
      "text": "Choose a discovered browser profile to configure.",
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
      "text": "Configuration is saved for the selected discovered browser profile without creating an operating-system profile.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "chrome-account-configuration",
          "effect": "creates",
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

# Discovered profile configured

## Trigger

Choose a discovered browser profile to configure.

## Outcome

Configuration is saved for the selected discovered browser profile without creating an operating-system profile.
