---
{
  "kind": "primary",
  "routes": {
    "offered": "Products"
  },
  "steps": [
    {
      "text": "Request restoring the selected offering.",
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
      "text": "The Archived product is restored Active by clearing its marker.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "product",
          "effect": "changes",
          "facts": [
            "Archive time",
            "Update time"
          ],
          "from": "Archived",
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

# Restore

## Trigger

Request restoring the selected offering.

## Outcome

The Archived product is restored Active by clearing its marker.
