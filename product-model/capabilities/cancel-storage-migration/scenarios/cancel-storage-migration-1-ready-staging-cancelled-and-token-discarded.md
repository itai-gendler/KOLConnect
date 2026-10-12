---
{
  "kind": "primary",
  "routes": {
    "offered": "Storage Migration"
  },
  "steps": [
    {
      "text": "Request cancellation of ready staging with the addressed token.",
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
      "text": "Valid addressed ready staging is cancelled and its confirmation discarded.",
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
          "to": "Cancelled"
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

# Ready staging cancelled and token discarded

## Trigger

Request cancellation of ready staging with the addressed token.

## Outcome

Valid addressed ready staging is cancelled and its confirmation discarded.
