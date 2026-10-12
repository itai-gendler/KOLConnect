---
{
  "domain": "mail-follow-up",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/mail-follow-up.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_follow_up_preferences.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/mail_follow_up_handler.py"
    }
  ]
}
---

# Mail Follow-up

One Creator/correspondent follow-up group with bounded chronology and independent snooze, stop and export decisions.

## Information kept

- **Creator association** — Canonical profile associated with a correspondent group.
- **Correspondent** — Normalized correspondent address.
- **Inbound chronology** — Available inbound chronology.
- **Outbound chronology** — Available outbound chronology.
- **Mail counts** — Available mail counts in the inspected history.
- **Waiting direction** — Derived waiting direction from reliable chronology.
- **Waiting age** — Derived age of the current waiting direction.
- **History confidence** — History completeness/uncertainty qualification.
- **Snooze until** — Future snooze preference, independently clearable.
- **Stopped time** — Stopped preference timestamp, independently clearable.
- **Export decision time** — Export-queue decision timestamp, retained on repeated addition and clearable by explicit removal or qualifying later Sent evidence.
