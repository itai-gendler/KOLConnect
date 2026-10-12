---
{
  "kind": "primary",
  "routes": {
    "offered": "Products"
  },
  "steps": [
    {
      "text": "Supply a required offering name and optional company/notes.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::products"
        }
      }
    },
    {
      "text": "A valid named promoted product is created Active with optional company/notes and recorded creation/update times.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "product",
          "effect": "creates",
          "facts": [
            "Identity",
            "Name",
            "Company",
            "Notes",
            "Creation time",
            "Update time",
            "Archive time"
          ],
          "to": "Active"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::products"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/products.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/product_repository.py"
    }
  ]
}
---

# Active Product created

## Trigger

Supply a required offering name and optional company/notes.

## Outcome

A valid named promoted product is created Active with optional company/notes and recorded creation/update times.
