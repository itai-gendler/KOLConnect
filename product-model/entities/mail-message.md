---
{
  "domain": "mail",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/mail_sync.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_inbox_facts.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/settings_handler.py"
    }
  ]
}
---

# Mail Message

An observed correspondence fact with historical mailbox provenance and matching evidence.

## Information kept

- **Observed message identity** — Deduplicated observed message identity.
- **Historical mailbox identity** — Mailbox identity retained even if live configuration is removed.
- **Mailbox generation** — Mailbox UID/generation provenance.
- **Addresses** — Observed sender/recipient addresses and account/creator match evidence.
- **Subject** — Observed subject.
- **Message time** — Message chronology time.
- **Observation time** — Time locally observed.
- **Available content** — Available bounded message content.
- **Direction** — Inbound or outbound direction.
- **Match evidence** — Reliable, unmatched or ambiguous identity evidence.
- **CRM-sync outcome** — Processed/skipped/failed CRM synchronization outcome.
