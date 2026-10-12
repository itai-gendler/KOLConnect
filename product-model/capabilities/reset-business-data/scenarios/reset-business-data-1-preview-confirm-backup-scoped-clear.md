---
{
  "kind": "primary",
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
      "text": "Within the backed-up scoped reset, remove the declared canonical, campaign and product records and supported parent-dependent history. Verify preservation before reporting success.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "creator-account",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "creator-snapshot",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "video-snapshot",
          "effect": "removes",
          "with": "creator-snapshot"
        },
        {
          "entity": "current-video",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "legacy-cooperation",
          "effect": "removes",
          "with": "creator"
        },
        {
          "entity": "product",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "campaign",
          "effect": "removes",
          "with": "product",
          "from": "Active"
        },
        {
          "entity": "campaign-creator",
          "effect": "removes",
          "with": "campaign",
          "from": "Active"
        },
        {
          "entity": "campaign-brief",
          "effect": "removes",
          "with": "campaign"
        },
        {
          "entity": "content-submission",
          "effect": "removes",
          "with": "campaign-creator",
          "from": "Pending"
        },
        {
          "entity": "actual-publication",
          "effect": "removes",
          "with": "campaign-creator"
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
          "place": "kolconnect-desktop::clean-reset"
        }
      }
    },
    {
      "text": "Within the same scoped reset, remove agencies and their owned contacts independently of canonical profile removal.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "agency",
          "effect": "removes"
        },
        {
          "entity": "agency-contact",
          "effect": "removes",
          "with": "agency"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::clean-reset"
        }
      }
    },
    {
      "text": "Within the same scoped reset, remove capture task artifacts and its owned results.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "capture-task",
          "effect": "removes",
          "from": "Created"
        },
        {
          "entity": "task-result",
          "as": "capture-result",
          "effect": "removes",
          "from": "Pending",
          "with": "capture-task"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::clean-reset"
        }
      }
    },
    {
      "text": "Within the same scoped reset, remove manual task artifacts and its owned results.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "manual-task",
          "effect": "removes",
          "from": "Manual created"
        },
        {
          "entity": "task-result",
          "as": "manual-result",
          "effect": "removes",
          "from": "Pending",
          "with": "manual-task"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::clean-reset"
        }
      }
    },
    {
      "text": "Within the same scoped reset, remove email recheck task artifacts and its owned results.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "removes",
          "from": "Email recheck created"
        },
        {
          "entity": "task-result",
          "as": "email-result",
          "effect": "removes",
          "from": "Pending",
          "with": "email-recheck-task"
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

# Preview/confirm/backup/scoped clear

## Trigger

Preview the declared clear/preserve scope and explicitly confirm the scoped reset.

## Outcome

The confirmed declared fourteen-sheet compatibility scope, task artifacts and designated JSON stores are cleared after validated backup; settings/metadata are preserved and verification succeeds.


## Edge cases

- The clear applies to declared records regardless of retained archive or human-review state. Controlled task removal includes all declared task artifacts; this does not establish a universal active-worker refusal or schema-6 wipe.
