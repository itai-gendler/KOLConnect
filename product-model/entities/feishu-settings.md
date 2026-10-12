---
{
  "singleton": true,
  "domain": "integrations",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/settings.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_sync_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/feishu_sync_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_chat_transport.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_chat_service.py"
    }
  ]
}
---

# Feishu Settings

The product's one Feishu connector and optional Chat configuration.

## Information kept

- **Connector identifiers** — Feishu application/base identifiers.
- **Protected secret** — Protected connector secret, preserved on masked saves.
- **Target tables** — Configured synchronization table identifiers.
- **Chat enabled** — Persisted optional Chat switch.
- **Configuration status** — Local configuration and validation outcome.
- **Transport status** — Long-connection lifecycle and sanitized failure information.
