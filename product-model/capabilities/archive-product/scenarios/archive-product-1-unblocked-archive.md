---
{
  "kind": "primary",
  "routes": {
    "offered": "Products"
  },
  "steps": [
    {
      "text": "Request archiving the selected offering.",
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
      "text": "With no active campaign references, the product becomes Archived.",
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
          "from": "Active",
          "to": "Archived"
        },
        {
          "entity": "campaign",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Product association",
            "Country",
            "Target platforms",
            "Start date",
            "End date",
            "Descriptive owner",
            "Budget",
            "Goal",
            "Notes",
            "Business status",
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

# Unblocked archive

## Trigger

Request archiving the selected offering.

## Outcome

With no active campaign references, the product becomes Archived.
