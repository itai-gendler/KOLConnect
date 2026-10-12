---
{
  "domain": "agencies",
  "relations": [
    {
      "entity": "agency-contact",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "creator",
      "verb": "represents",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/agencies.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/agency_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_agency_repository.py"
    }
  ]
}
---

# Agency

An agency whose profile, contacts and associated Creator work can be inspected.

## Information kept

- **Identity** — Addressed agency identity.
- **Name** — Agency name.
- **Country** — Recorded country or region.
- **Website** — Agency website.
- **Contact details** — Agency email and other contact details.
- **Cooperation stage** — Recorded cooperation stage.
- **Descriptive owner** — Descriptive responsibility text.
- **Tags** — Agency tags.
- **Notes** — Agency notes.
- **Resources** — Recorded agency resource description.
- **Follow-up times** — Recorded last contact and next follow-up times.
