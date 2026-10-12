---
{
  "domain": "campaigns",
  "relations": [
    {
      "entity": "campaign-creator",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "campaign-brief",
      "verb": "has",
      "cardinality": "one-to-one"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaigns.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/campaign_repository.py"
    }
  ]
}
---

# Campaign

A campaign associated with a promoted Product, with profile facts, cooperation and content requirements.

## Information kept

- **Identity** — Addressed campaign identity.
- **Name** — Campaign name.
- **Product association** — Associated promoted product.
- **Country** — Target country or region.
- **Target platforms** — Configured target social platforms.
- **Start date** — Planned campaign start date.
- **End date** — Planned campaign end date.
- **Descriptive owner** — Descriptive campaign responsibility.
- **Budget** — Recorded budget amount without an established currency unit.
- **Goal** — Recorded campaign goal.
- **Notes** — Campaign notes.
- **Business status** — Recorded draft, sourcing, running or completed status.
- **Archive time** — Archive marker independent of business status.

## States

### Active

The archive marker is empty.

### Archived

An archive marker is retained independently of business status.
