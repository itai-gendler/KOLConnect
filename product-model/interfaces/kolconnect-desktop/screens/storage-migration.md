---
{
  "entities": [
    {
      "entity": "data-settings",
      "shows": [
        "Configured source location",
        "Current authority",
        "Current source information"
      ]
    },
    {
      "entity": "storage-migration",
      "shows": [
        "Migration identity",
        "Prepared source",
        "Source fingerprint",
        "Validation results",
        "Counts",
        "Digests",
        "Backup",
        "Staged target",
        "Phase",
        "Timing",
        "Failure",
        "Activation result"
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
  ]
}
---

# Storage Migration

Addressed migration, phase, source validation, backup/staging readiness, confirmation and recovery.
