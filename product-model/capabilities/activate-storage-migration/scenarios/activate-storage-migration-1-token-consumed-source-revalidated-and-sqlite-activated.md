---
{
  "kind": "primary",
  "routes": {
    "offered": "Storage Migration"
  },
  "steps": [
    {
      "text": "Confirm the addressed prepared source using its current valid token.",
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
      "text": "A valid addressed token is consumed, source fingerprint revalidated and staged SQLite activated; the original workbook is retained.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "storage-migration",
          "effect": "changes",
          "facts": [
            "Phase",
            "Timing"
          ],
          "from": "Ready for activation",
          "to": "Activation in progress"
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
      "text": "Commit staged SQLite authority and complete the addressed activation while retaining the source workbook.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "data-settings",
          "effect": "changes",
          "facts": [
            "Current authority",
            "Current source information"
          ]
        },
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

# Token consumed, source revalidated and SQLite activated

## Trigger

Confirm the addressed prepared source using its current valid token.

## Outcome

A valid addressed token is consumed, source fingerprint revalidated and staged SQLite activated; the original workbook is retained.
