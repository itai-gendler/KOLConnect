---
{
  "appliesTo": [
    {
      "type": "context",
      "context": {
        "place": "kolconnect-desktop"
      }
    },
    {
      "type": "context",
      "context": {
        "place": "kolconnect-chrome-extension"
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/local_request_security.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/server.py"
    }
  ]
}
---

# Local transport enforces Host and mutation Origin constraints

Local service requests enforce permitted Host and mutation Origin constraints, with restricted supported extension exceptions and migration Origin validation. This is transport validation, not an application login or RBAC hierarchy.
