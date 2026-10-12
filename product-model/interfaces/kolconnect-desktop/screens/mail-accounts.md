---
{
  "entities": [
    {
      "entity": "mail-account",
      "shows": [
        "Configuration identity",
        "Mailbox identity",
        "Provider",
        "Connection endpoints",
        "Usernames",
        "Sender details",
        "Enabled",
        "Protected credentials"
      ],
      "collects": [
        "Mailbox identity",
        "Provider",
        "Connection endpoints",
        "Usernames",
        "Sender details",
        "Enabled",
        "Protected credentials"
      ]
    }
  ],
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

# Mail Accounts

Connection configuration, enabled state, masked credentials and test outcomes

 configuration/secrets.
