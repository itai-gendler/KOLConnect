---
{
  "kind": "edge",
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
      "text": "Failed verification restores staged authoritative data, designated JSON and task artifacts; incomplete rollback/cleanup is reported as failure rather than success.",
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

# Failed verification restores staged data

## Trigger

Preview the declared clear/preserve scope and explicitly confirm the scoped reset.

## Outcome

Failed verification restores staged authoritative data, designated JSON and task artifacts; incomplete rollback/cleanup is reported as failure rather than success.
