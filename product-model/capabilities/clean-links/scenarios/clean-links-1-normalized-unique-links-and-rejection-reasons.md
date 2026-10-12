---
{
  "kind": "primary",
  "routes": {
    "offered": "Link Cleanup"
  },
  "steps": [
    {
      "text": "Supply profile links for normalization and classification.",
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
      "text": "Supported links are normalized and deduplicated, with rejected inputs and reasons disclosed as transient output.",
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

# Normalized unique links and rejection reasons

## Trigger

Supply profile links for normalization and classification.

## Outcome

Supported links are normalized and deduplicated, with rejected inputs and reasons disclosed as transient output.
