---
{
  "entities": [
    {
      "entity": "creator",
      "shows": [
        "Contact details"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Account email"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/creator_url_resolver.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/creator_handler.py"
    }
  ]
}
---

# Link Cleanup

Supplied links/emails, transient normalization/classification and canonical address matches.
