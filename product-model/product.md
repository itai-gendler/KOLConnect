---
{
  "id": "kolconnect",
  "summary": "A local workbench for collecting creator accounts, reviewing captures, maintaining canonical Creators, recording campaign cooperation and publications, and synchronizing bounded correspondence and selected information.",
  "category": "creator-relationship-management",
  "tags": [
    "creator",
    "campaign",
    "local-workbench"
  ],
  "languages": [
    "zh",
    "en"
  ],
  "limitations": [
    "Actual publications are recorded; the product does not publish content to social platforms.",
    "Inbox synchronization observes bounded correspondence without sending mail.",
    "Reference USD conversions use manually configured rates.",
    "Production publication refresh currently returns unavailable or deferred."
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "README.md"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/launcher.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/index.html"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/manifest.json"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_chat_transport.py"
    },
    {
      "kind": "code",
      "role": "context",
      "target": "LICENSE"
    }
  ],
  "license": "MIT"
}
---

# KOLConnect

KOLConnect is a local workbench for collecting creator-account information, reviewing captures, maintaining canonical Creators, managing campaign cooperation and recorded publications, inspecting correspondence, and synchronizing selected information to Feishu and Google Sheets.

## Intent

Keep canonical person/business identity distinct from platform identity, publication plans distinct from actual records, and original commercial currencies distinct from reference conversions.
