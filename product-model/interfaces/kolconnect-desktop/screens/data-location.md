---
{
  "entities": [
    {
      "entity": "data-settings",
      "shows": [
        "Configured source location",
        "Current authority",
        "Current source information"
      ],
      "collects": [
        "Configured source location"
      ]
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

# Data Location

Configured workbook location, current authority/source information and backup outcome.
