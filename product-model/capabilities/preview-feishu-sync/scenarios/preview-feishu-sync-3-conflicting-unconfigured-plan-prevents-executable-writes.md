---
{
  "kind": "validation",
  "routes": {
    "offered": "Feishu Integration"
  },
  "steps": [
    {
      "text": "Request a fresh Feishu synchronization preview.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::feishu-integration"
        }
      }
    },
    {
      "text": "An unconfigured or conflicting plan is nonexecutable and performs no planned remote writes.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
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
        },
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Language",
            "Content category",
            "Biography",
            "Contact details",
            "Tags",
            "Notes",
            "Descriptive owner",
            "Agency association",
            "Contact association",
            "Business status",
            "Archive time",
            "Update time",
            "Linked review task"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "reads",
          "facts": [
            "Canonical identity",
            "Platform",
            "Profile identity",
            "Username",
            "Creator association",
            "Account email",
            "Followers",
            "Latest post",
            "Capture status",
            "Capture time",
            "Source",
            "Notes"
          ]
        },
        {
          "entity": "agency",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Country",
            "Website",
            "Contact details",
            "Cooperation stage",
            "Descriptive owner",
            "Tags",
            "Notes",
            "Resources",
            "Follow-up times"
          ]
        },
        {
          "entity": "agency-contact",
          "effect": "reads",
          "facts": [
            "Identity",
            "Agency association",
            "Name",
            "Position",
            "Addresses",
            "Language",
            "Status",
            "Descriptive owner",
            "Notes",
            "Follow-up times",
            "Source"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::feishu-integration"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_chat_message_adapter.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/assistant_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/assistant_confirmation_store.py"
    }
  ]
}
---

# Conflicting/unconfigured plan prevents executable writes

## Trigger

Request a fresh Feishu synchronization preview.

## Outcome

An unconfigured or conflicting plan is nonexecutable and performs no planned remote writes.
