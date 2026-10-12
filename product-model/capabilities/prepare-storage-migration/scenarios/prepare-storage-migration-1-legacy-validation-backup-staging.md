---
{
  "kind": "primary",
  "routes": {
    "offered": "Storage Migration"
  },
  "steps": [
    {
      "text": "Request validation, backup and staging of the current legacy source.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::storage-migration"
        }
      }
    },
    {
      "text": "Valid legacy authority at the canonical root is validated, backed up and staged as SQLite, leaving the migration Ready for activation.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "storage-migration",
          "effect": "creates",
          "facts": [
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
          ],
          "to": "Preparing"
        },
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
          "place": "kolconnect-desktop::storage-migration"
        }
      }
    },
    {
      "text": "Validation, backup and staged-target comparison finish; the addressed migration becomes Ready for activation.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "storage-migration",
          "effect": "changes",
          "facts": [
            "Phase",
            "Validation results",
            "Counts",
            "Digests",
            "Backup",
            "Staged target",
            "Timing"
          ],
          "from": "Preparing",
          "to": "Ready for activation"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::storage-migration"
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

# Legacy validation/backup/staging

## Trigger

Request validation, backup and staging of the current legacy source.

## Outcome

Valid legacy authority at the canonical root is validated, backed up and staged as SQLite, leaving the migration Ready for activation.
