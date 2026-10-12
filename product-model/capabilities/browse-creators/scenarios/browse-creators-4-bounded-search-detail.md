---
{
  "kind": "primary",
  "routes": {
    "offered": "Feishu Chat"
  },
  "steps": [
    {
      "text": "Supply a search/filter or select the identity whose available detail is needed.",
      "kind": "actor",
      "actor": "feishu-chat-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "feishu-chat-assistant"
        }
      }
    },
    {
      "text": "Chat returns at most its bounded matching profiles or supported selected detail, with redacted fields.",
      "kind": "product",
      "actor": "feishu-chat-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Name",
            "Country",
            "Language"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "reads",
          "facts": [
            "Platform",
            "Profile identity",
            "Username",
            "Followers"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "feishu-chat-assistant"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/storage/sqlite_creator_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/creator-library-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/content/floating_assistant.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/analysis_session.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/content_analysis.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/diagnostics.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/services/local_api.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/server.py#import_extension_capture"
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
      "target": "app/services/feishu_chat_transport.py"
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

# Bounded search/detail

## Trigger

Supply a search/filter or select the identity whose available detail is needed.

## Outcome

Chat returns at most its bounded matching profiles or supported selected detail, with redacted fields.
