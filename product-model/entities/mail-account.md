---
{
  "domain": "mail-accounts",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/settings_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_auth_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/mail_secret_storage.py"
    }
  ]
}
---

# Mail Account

A configured mailbox selected for observation and connection testing; synchronization observes mail without sending.

## Information kept

- **Configuration identity** — Addressed mailbox configuration identity.
- **Mailbox identity** — Configured mailbox address/identity.
- **Provider** — Configured provider.
- **Connection endpoints** — IMAP/SMTP host, port and secure connection settings.
- **Usernames** — Connection usernames.
- **Sender details** — Configured sender name/address.
- **Enabled** — Mailbox-selection flag for synchronization.
- **Protected credentials** — Native protected secret, disclosed only in masked form.
