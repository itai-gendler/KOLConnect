---
{
  "entities": [
    {
      "entity": "product",
      "shows": [
        "Identity",
        "Name",
        "Company",
        "Notes",
        "Creation time",
        "Update time",
        "Archive time"
      ],
      "collects": [
        "Name",
        "Company",
        "Notes"
      ]
    },
    {
      "entity": "campaign",
      "shows": [
        "Identity",
        "Name",
        "Product association",
        "Archive time"
      ]
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

# Products

Product profile, archive state and campaign references

 Product facts.
