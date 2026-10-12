---
{
  "kind": "primary",
  "routes": {
    "offered": "Products"
  },
  "steps": [
    {
      "text": "Supply supported name, company and notes edits for the active offering.",
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
      "text": "The Active product's supported name, company and notes are saved.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "product",
          "effect": "changes",
          "facts": [
            "Name",
            "Company",
            "Notes",
            "Update time"
          ]
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

# Active Product save

## Trigger

Supply supported name, company and notes edits for the active offering.

## Outcome

The Active product's supported name, company and notes are saved.
