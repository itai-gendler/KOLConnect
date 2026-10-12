---
{
  "kind": "validation",
  "routes": {
    "offered": "Clean Reset"
  },
  "steps": [
    {
      "text": "Preview the declared clear/preserve scope and explicitly confirm the scoped reset.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::clean-reset"
        }
      }
    },
    {
      "text": "Missing confirmation, schema/root incompatibility or a transaction blocker refuses the reset.",
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
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::clean-reset"
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
      "target": "app/http_handlers/clean_reset_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/clean_reset_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_workbook_store.py"
    }
  ]
}
---

# Confirmation/schema/root/transaction blocker refused

## Trigger

Preview the declared clear/preserve scope and explicitly confirm the scoped reset.

## Outcome

Missing confirmation, schema/root incompatibility or a transaction blocker refuses the reset.
