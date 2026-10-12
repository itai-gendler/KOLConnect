---
{
  "kind": "validation",
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
      "text": "Invalid or ambiguous migration state is refused without an unsupported authority choice.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
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

# Invalid/ambiguous migration state refused

## Trigger

Request recovery of the addressed interrupted activation.

## Outcome

Invalid or ambiguous migration state is refused without an unsupported authority choice.
