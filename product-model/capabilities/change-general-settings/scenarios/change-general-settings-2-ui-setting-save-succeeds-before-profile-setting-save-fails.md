---
{
  "kind": "edge",
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
      "text": "The earlier language/UI settings save remains successful when the later default-profile save fails.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "general-settings",
          "effect": "changes",
          "facts": [
            "Preferred language"
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

# UI-setting save succeeds before profile-setting save fails

## Trigger

Choose language and default capture-profile settings to save.

## Outcome

The earlier language/UI settings save remains successful when the later default-profile save fails.
