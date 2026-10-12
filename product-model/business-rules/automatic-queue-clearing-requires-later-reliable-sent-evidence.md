---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mail-follow-up",
      "effect": "changes",
      "facts": [
        "Export decision time"
      ]
    },
    {
      "type": "entity",
      "id": "mail-message",
      "effect": "reads",
      "facts": [
        "Direction",
        "Match evidence",
        "Addresses",
        "Message time",
        "Observation time"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up_preferences.py#reconcile_export_queue_from_sent"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_inbox_facts.py"
    }
  ]
}
---

# Automatic queue clearing requires later reliable Sent evidence

Automatic export clearing requires reliable matched outbound/Sent evidence to the same correspondent, with both message and local-observation times at or after the persisted decision time. Inbound, ambiguous, malformed or old-backfill evidence does not clear intent.
