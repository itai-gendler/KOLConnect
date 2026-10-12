---
{
  "domain": "campaigns",
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

# Content Submission

An addressed submitted content reference within campaign participation, with human decisions independent of derived first-pass findings.

## Information kept

- **Submission identity** — Addressed content-submission identity.
- **Cooperation association** — Owning campaign participation.
- **Optional Account** — Optional supplied account association; a supplied association must refer to an existing account.
- **Content type** — Script, copy, video draft or other content type.
- **Content reference** — Submitted textual reference or URL.
- **Submission time** — Time of submission.
- **Submitted by** — Descriptive submitter value.
- **Source** — Submission source, defaulting to manual where omitted.
- **Human review** — Pending, Approved, Changes requested or Rejected human decision.
- **Review note** — Human review note.
- **First-pass findings** — Deterministic first-pass findings with requirement, risk, reason and suggested human confirmation.

## States

### Pending

Human review has not decided the result.

### Approved

The human review decision is approval.

### Changes requested

Human review requests changes.

### Rejected

Human review has rejected the result.
