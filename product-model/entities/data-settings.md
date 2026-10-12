---
{
  "singleton": true,
  "domain": "data",
  "relations": [
    {
      "entity": "storage-migration",
      "verb": "has",
      "cardinality": "one-to-many"
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

# Data Settings

The product's configured data location and current authority description.

## Information kept

- **Configured source location** — Configured workbook/source path.
- **Current authority** — Legacy workbook or activated SQLite authority.
- **Current source information** — Current authority/source description used by backup and migration.
