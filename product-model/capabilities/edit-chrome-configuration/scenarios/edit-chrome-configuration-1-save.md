---
{
  "kind": "primary",
  "routes": {
    "offered": "Chrome Accounts"
  },
  "steps": [
    {
      "text": "Supply the selected browser configuration's alias and notes.",
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
      "text": "The selected saved alias and notes are replaced.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "chrome-account-configuration",
          "effect": "changes",
          "facts": [
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

# Save

## Trigger

Supply the selected browser configuration's alias and notes.

## Outcome

The selected saved alias and notes are replaced.
