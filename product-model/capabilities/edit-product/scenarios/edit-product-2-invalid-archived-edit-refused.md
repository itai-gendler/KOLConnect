---
{
  "kind": "validation",
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
      "text": "Invalid facts or editing an Archived product is refused without changing its profile.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "product",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Company",
            "Notes",
            "Creation time",
            "Update time",
            "Archive time"
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

# Invalid/Archived edit refused

## Trigger

Supply supported name, company and notes edits for the active offering.

## Outcome

Invalid facts or editing an Archived product is refused without changing its profile.
