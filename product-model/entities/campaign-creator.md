---
{
  "domain": "campaigns",
  "relations": [
    {
      "entity": "creator-account",
      "verb": "selects",
      "cardinality": "many-to-many"
    },
    {
      "entity": "content-submission",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "actual-publication",
      "verb": "records",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaign-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/campaign_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/publication.py"
    }
  ]
}
---

# Campaign Creator

An individually addressed Creator's participation in one Campaign, holding cooperation terms, execution accounts, plans and recorded outcomes.

## Information kept

- **Participation identity** — Addressed campaign participation identity.
- **Campaign association** — Owning campaign.
- **Creator association** — Participating canonical profile.
- **Execution Accounts** — Selected execution account identities.
- **Cooperation stage** — Ordinary cooperation records pending_contact, contacted, quoted, negotiating, agreed, executing, completed or rejected; direct-execution stage text is less constrained.
- **Quote currency** — Recorded three-letter quote currency.
- **Quote unit amount** — Finite nonnegative structured quote amount per pricing unit.
- **Quote quantity** — Positive integer structured quote quantity.
- **Pricing unit** — Video, post, reel, short, story, package or other pricing unit.
- **Quote total** — Structured amount times quantity, or retained compatibility quote amount.
- **Cost** — Recorded cooperation cost counted once for participation.
- **Cost currency** — Explicit cost currency, implemented quote-currency fallback or unknown legacy currency.
- **Planned publication dates** — Selected planned dates independent of actual publications.
- **Compatibility publication facts** — Compatibility publication date, link and count derived by the inspected plan/publication paths.
- **Recorded metrics** — Recorded cooperation views and other supported metric inputs.
- **Recorded ROI** — Recorded cooperation ROI used separately from publication ROI.
- **Performance notes** — Recorded performance commentary.
- **Responsibility** — Descriptive execution owner.
- **Next action** — Recorded next action.
- **Due date** — Execution due date.
- **Waiting on** — Creator, internal, client, self or none waiting direction.
- **Decision needed** — Recorded need-for-decision flag.
- **Last progress time** — Time of meaningful execution progress.
- **Archive time** — Participation archive marker.

## States

### Active

The archive marker is empty.

### Archived

An archive marker is retained independently of business status.
