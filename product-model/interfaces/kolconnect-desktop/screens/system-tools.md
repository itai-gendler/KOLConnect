---
{
  "entities": [
    {
      "entity": "data-settings",
      "shows": [
        "Configured source location",
        "Current authority",
        "Current source information"
      ]
    },
    {
      "entity": "feishu-settings",
      "shows": [
        "Configuration status"
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

# System Tools

Local workbook/configuration/recent-extension-import health results.
