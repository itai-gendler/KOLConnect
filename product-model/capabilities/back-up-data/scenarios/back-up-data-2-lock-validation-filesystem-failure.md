---
{
  "kind": "edge",
  "routes": {
    "offered": "Data Location"
  },
  "steps": [
    {
      "text": "Request a retained validated backup of current authoritative data.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::data-location"
        }
      }
    },
    {
      "text": "Lock, source-validation or filesystem failure is reported without claiming a usable completed backup.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "data-settings",
          "effect": "reads",
          "facts": [
            "Configured source location",
            "Current authority",
            "Current source information"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::data-location"
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
      "target": "app/services/workbook_backup_service.py"
    }
  ]
}
---

# Lock/validation/filesystem failure

## Trigger

Request a retained validated backup of current authoritative data.

## Outcome

Lock, source-validation or filesystem failure is reported without claiming a usable completed backup.
