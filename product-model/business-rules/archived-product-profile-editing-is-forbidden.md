---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product",
      "effect": "changes",
      "facts": [
        "Name",
        "Company",
        "Notes"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::products"
        }
      ],
      "from": "Archived"
    }
  ],
  "permits": [],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/product_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/products.js"
    }
  ]
}
---

# Archived Product profile editing is forbidden

An Archived Product's Name, Company and Notes cannot be directly edited in Products; restore is a separate operation.
