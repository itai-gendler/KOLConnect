---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "check-storage-migration",
      "contexts": [
        {
          "place": "kolconnect-desktop::storage-migration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "prepare-storage-migration",
      "contexts": [
        {
          "place": "kolconnect-desktop::storage-migration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "activate-storage-migration",
      "contexts": [
        {
          "place": "kolconnect-desktop::storage-migration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "cancel-storage-migration",
      "contexts": [
        {
          "place": "kolconnect-desktop::storage-migration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "recover-storage-migration",
      "contexts": [
        {
          "place": "kolconnect-desktop::storage-migration"
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

# Migration requires prepared-source confirmation and recoverable authority

Production migration requires canonical root and prepared legacy authority, validated source/backup/staging, addressed confirmation and source-fingerprint revalidation. Token expiry/mismatch or changed source prevents activation. Recovery distinguishes pre-commit readiness from post-commit SQLite activation; original workbook is retained. Preparation does not establish a separate active-capture-worker prohibition.
