---
{
  "kind": "primary",
  "routes": {
    "offered": "Runtime Log"
  },
  "steps": [
    {
      "text": "Request exposed runtime activity.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::runtime-log"
        }
      }
    },
    {
      "text": "Exposed runtime activity returns event time, scope and message.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "runtime-log",
          "effect": "reads",
          "facts": [
            "Event time",
            "Scope",
            "Message"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::runtime-log"
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
      "target": "app/app_logging.py"
    }
  ]
}
---

# Exposed runtime activity

## Trigger

Request exposed runtime activity.

## Outcome

Exposed runtime activity returns event time, scope and message.
