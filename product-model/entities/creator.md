---
{
  "domain": "creator-library",
  "relations": [
    {
      "entity": "creator-account",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "creator-snapshot",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "current-video",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "legacy-cooperation",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "campaign-creator",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "mail-follow-up",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    }
  ]
}
---

# Creator

The canonical person or business subject in the Creator Library, distinct from every platform account it owns. It may remain with no accounts.

## Information kept

- **Identity** — Canonical person/business subject identity, independent of platform accounts.
- **Name** — Displayed canonical profile name.
- **Country** — Recorded country or region.
- **Language** — Recorded content language.
- **Content category** — Recorded category of content.
- **Biography** — Canonical biographical text.
- **Contact details** — Recorded email and other contact addresses, including WhatsApp where supplied.
- **Tags** — Manually retained profile tags.
- **Notes** — Manually retained profile notes.
- **Descriptive owner** — Descriptive responsibility text, without an authorization role.
- **Agency association** — Selected agency, when associated.
- **Contact association** — Selected agency contact, when associated.
- **Business status** — Recorded discovered, contacted, negotiating, cooperating, completed or rejected status.
- **Archive time** — Time of archiving, empty for an active profile.
- **Creation time** — Canonical creation time retained by current SQLite records and used by its recent-new overview projection.
- **Update time** — Time of the most recent canonical update.
- **Linked review task** — Existing task association used to open review results.

## States

### Active

The archive marker is empty.

### Archived

An archive marker is retained independently of business status.
