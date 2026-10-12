---
{
  "domain": "review-results",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_result_mapper.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    }
  ]
}
---

# Task Result

One account result owned by one task family, with capture outcome, confirmed edits and human review kept independently.

## Information kept

- **Task/account identity** — Identity of one account result within its owning task family.
- **Capture facts** — Available captured profile/contact/metric facts.
- **Capture status** — Capture outcome independent of review decision.
- **Capture error** — Recorded capture failure or absence reason.
- **Confirmed edits** — Supported manually confirmed field edits.
- **Review decision** — Pending, Approved or Rejected human review decision.
- **Review reason** — Optional rejection/review reason.
- **Review time** — Time of human review.
- **Creator import linkage** — Canonical profile import identity and outcome.
- **Account import linkage** — Canonical account import identity and outcome.

## States

### Pending

Human review has not decided the result.

### Approved

The human review decision is approval.

### Rejected

Human review has rejected the result.
