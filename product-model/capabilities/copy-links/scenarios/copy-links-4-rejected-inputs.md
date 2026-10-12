---
{
  "kind": "primary",
  "routes": {
    "offered": "Link Cleanup"
  },
  "steps": [
    {
      "text": "Select original, unfinished, cleaned or rejected links for copying.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::link-cleanup"
        }
      }
    },
    {
      "text": "The rejected-input output with the currently available classification is copied.",
      "kind": "product",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::link-cleanup"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/task_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/adapters/task_manager_adapter.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/task_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/creator_url_resolver.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/creator_handler.py"
    }
  ]
}
---

# Rejected inputs

## Trigger

Select original, unfinished, cleaned or rejected links for copying.

## Outcome

The rejected-input output with the currently available classification is copied.
