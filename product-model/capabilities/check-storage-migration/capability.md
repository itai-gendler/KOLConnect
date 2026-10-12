---
{
  "availability": [
    {
      "place": "kolconnect-desktop"
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
      "target": "app/http_handlers/storage_migration_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/production_migration_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/migration.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/authority.py"
    }
  ],
  "domain": "advanced"
}
---

# Check storage migration

Inspect current storage authority and the addressed migration's phase, source, backup and confirmation readiness.
