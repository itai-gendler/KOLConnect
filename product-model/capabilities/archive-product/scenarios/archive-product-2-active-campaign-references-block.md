---
{
  "kind": "validation",
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
      "text": "Active campaign references block archive and preserve the current marker.",
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

# Active Campaign references block

## Trigger

Request archiving the selected offering.

## Outcome

Active campaign references block archive and preserve the current marker.
