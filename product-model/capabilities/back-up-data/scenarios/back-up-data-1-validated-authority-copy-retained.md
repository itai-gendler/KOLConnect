---
{
  "kind": "primary",
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
      "text": "A validated copy of current authority is retained, with managed retention of ten manual backups.",
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

# Validated authority copy retained

## Trigger

Request a retained validated backup of current authoritative data.

## Outcome

A validated copy of current authority is retained, with managed retention of ten manual backups.
