---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "back-up-data",
      "contexts": [
        {
          "place": "kolconnect-desktop::data-location"
        }
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

# Manual backup preserves a validated authority copy

Manual backup locks and validates current authority, retains a usable separate copy and keeps ten managed manual backups. A failed copy/validation is not a successful backup.
