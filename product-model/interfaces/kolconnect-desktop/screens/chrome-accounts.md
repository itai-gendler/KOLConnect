---
{
  "entities": [
    {
      "entity": "chrome-account-configuration",
      "shows": [
        "Discovered profile identity",
        "Availability",
        "Alias",
        "Notes"
      ],
      "collects": [
        "Alias",
        "Notes"
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
    }
  ]
}
---

# Chrome Accounts

Discovered profile availability and saved configuration

 aliases/notes.
