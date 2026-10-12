---
{
  "kind": "primary",
  "routes": {
    "offered": "Storage Migration"
  },
  "steps": [
    {
      "text": "Request recovery of the addressed interrupted activation.",
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
      "text": "Recovery after the commit point completes SQLite activation and reports Completed.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "storage-migration",
          "effect": "changes",
          "facts": [
            "Phase",
            "Timing",
            "Activation result"
          ],
          "from": "Activation in progress",
          "to": "Completed"
        },
        {
          "entity": "data-settings",
          "effect": "changes",
          "facts": [
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

# Post-commit recovery completes SQLite activation

## Trigger

Request recovery of the addressed interrupted activation.

## Outcome

Recovery after the commit point completes SQLite activation and reports Completed.
