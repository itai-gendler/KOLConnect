---
{
  "kind": "primary",
  "routes": {
    "offered": "System Tools"
  },
  "steps": [
    {
      "text": "Request local workbook, configuration and recent-import checks.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::system-tools"
        }
      }
    },
    {
      "text": "Local configured-workbook/declared-sheet/configuration/recent-extension-import checks are returned without remote connector requests.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "data-settings",
          "effect": "reads",
          "facts": [
            "Configured source location",
            "Current authority",
            "Current source information"
          ]
        },
        {
          "entity": "feishu-settings",
          "effect": "reads",
          "facts": [
            "Connector identifiers",
            "Protected secret",
            "Target tables",
            "Chat enabled",
            "Configuration status",
            "Transport status"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::system-tools"
        }
      }
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

# Workbook/configuration/recent-import checks without remote calls

## Trigger

Request local workbook, configuration and recent-import checks.

## Outcome

Local configured-workbook/declared-sheet/configuration/recent-extension-import checks are returned without remote connector requests.
