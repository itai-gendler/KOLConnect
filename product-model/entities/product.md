---
{
  "domain": "products",
  "relations": [
    {
      "entity": "campaign",
      "verb": "is-promoted-by",
      "cardinality": "one-to-many"
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

# Product

A promoted product whose profile and campaign references remain visible when archived.

## Information kept

- **Identity** — Addressed promoted product identity.
- **Name** — Product name.
- **Company** — Company associated with the product.
- **Notes** — Product notes.
- **Creation time** — Creation time.
- **Update time** — Last profile-update time.
- **Archive time** — Archive marker independent of campaign references.

## States

### Active

The archive marker is empty.

### Archived

An archive marker is retained independently of business status.
