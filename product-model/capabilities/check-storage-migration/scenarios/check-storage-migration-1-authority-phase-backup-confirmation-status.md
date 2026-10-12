---
{
  "kind": "primary",
  "routes": {
    "offered": "Storage Migration"
  },
  "steps": [
    {
      "text": "Request authority and addressed migration status.",
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
      "text": "Authority, addressed phase, backup/staging and confirmation readiness are disclosed.",
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

# Authority/phase/backup/confirmation status

## Trigger

Request authority and addressed migration status.

## Outcome

Authority, addressed phase, backup/staging and confirmation readiness are disclosed.
