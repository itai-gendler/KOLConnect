---
{
  "kind": "validation",
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
      "text": "Invalid required facts are refused before creation.",
      "kind": "product",
      "actor": "local-user",
      "entities": [],
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

# Invalid required facts refused

## Trigger

Supply a required offering name and optional company/notes.

## Outcome

Invalid required facts are refused before creation.
