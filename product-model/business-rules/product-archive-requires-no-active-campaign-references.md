---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "archive-product",
      "contexts": [
        {
          "place": "kolconnect-desktop::products"
        }
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

# Product archive requires no active Campaign references

Active Campaign references prevent Product archive. Reference validation is an integrity condition, not a permission grant.
