---
{
  "kind": "validation",
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
      "text": "Invalid authority/root/source or an incompatible in-progress phase is refused without preparing a new executable target.",
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
        },
        {
          "entity": "storage-migration",
          "effect": "reads",
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
          ]
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

# Invalid authority/root/source/in-progress phase refused

## Trigger

Request validation, backup and staging of the current legacy source.

## Outcome

Invalid authority/root/source or an incompatible in-progress phase is refused without preparing a new executable target.
