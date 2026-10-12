---
{
  "domain": "agencies",
  "relations": [
    {
      "entity": "creator",
      "verb": "is-associated-with",
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

# Agency Contact

An individually addressed agency contact with communication and follow-up facts.

## Information kept

- **Identity** — Addressed contact identity.
- **Agency association** — Associated agency.
- **Name** — Contact name.
- **Position** — Contact position.
- **Addresses** — Recorded email and other contact addresses.
- **Language** — Recorded communication language.
- **Status** — Recorded contact status.
- **Descriptive owner** — Descriptive responsibility text.
- **Notes** — Contact notes.
- **Follow-up times** — Recorded contact and follow-up times.
- **Source** — Contact source description.
