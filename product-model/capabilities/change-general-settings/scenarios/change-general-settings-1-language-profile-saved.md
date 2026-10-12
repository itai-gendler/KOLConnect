---
{
  "kind": "primary",
  "routes": {
    "offered": "General Settings"
  },
  "steps": [
    {
      "text": "Choose language and default capture-profile settings to save.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::general-settings"
        }
      }
    },
    {
      "text": "The preferred language and default capture profile are saved through their supported settings paths.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "general-settings",
          "effect": "changes",
          "facts": [
            "Preferred language",
            "Default capture profile"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::general-settings"
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

# Language/profile saved

## Trigger

Choose language and default capture-profile settings to save.

## Outcome

The preferred language and default capture profile are saved through their supported settings paths.
