---
{
  "kind": "validation",
  "routes": {
    "offered": "Creator Library"
  },
  "steps": [
    {
      "text": "Supply the import workbook for validation.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
    },
    {
      "text": "An invalid batch is rejected before any imported canonical identity is created.",
      "kind": "product",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::creator-library"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_batch_import.py"
    }
  ]
}
---

# Invalid batch makes no import

## Trigger

Supply the import workbook for validation.

## Outcome

An invalid batch is rejected before any imported canonical identity is created.
