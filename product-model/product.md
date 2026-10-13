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
    "Data is kept in a local database on the person's own computer, and the workbench is served only to that computer.",
    "The local database stays authoritative; Feishu Bitable receives a one-way replica of Creator and account information.",
    "Inbox synchronization reads selected mailboxes without changing their messages.",
    "Mixed-currency amounts are never added into one total; USD conversions use manually configured reference rates."
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

Manage overseas creators, campaign cooperation and publications in one local workbench, keeping each Creator distinct from their platform accounts, planned publication distinct from actual evidence and original currencies distinct from USD conversions.
