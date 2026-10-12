---
{
  "kind": "primary",
  "routes": {
    "offered": "Link Cleanup"
  },
  "steps": [
    {
      "text": "Request copying the classified unrecorded email output.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::link-cleanup"
        }
      }
    },
    {
      "text": "The currently classified unrecorded emails are copied without creating canonical facts.",
      "kind": "product",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::link-cleanup"
        }
      }
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

# Unrecorded output copied

## Trigger

Request copying the classified unrecorded email output.

## Outcome

The currently classified unrecorded emails are copied without creating canonical facts.
