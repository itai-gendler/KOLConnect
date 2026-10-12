---
{
  "kind": "primary",
  "routes": {
    "offered": "Creator Library"
  },
  "steps": [
    {
      "text": "Request the import workbook template.",
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
      "text": "The import template is downloaded as XLSX without creating canonical data.",
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

# XLSX template

## Trigger

Request the import workbook template.

## Outcome

The import template is downloaded as XLSX without creating canonical data.
