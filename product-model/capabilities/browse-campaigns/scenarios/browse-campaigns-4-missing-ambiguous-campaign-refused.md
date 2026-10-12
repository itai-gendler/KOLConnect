---
{
  "kind": "validation",
  "routes": {
    "offered": "Feishu Chat"
  },
  "steps": [
    {
      "text": "Request activity inventory or select activity detail.",
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
      "text": "Missing or ambiguous conversational campaign identity is refused without selecting an arbitrary campaign.",
      "kind": "product",
      "actor": "feishu-chat-user",
      "entities": [
        {
          "entity": "campaign",
          "effect": "reads",
          "facts": [
            "Name",
            "Product association",
            "Business status",
            "Target platforms",
            "Country"
          ]
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "campaign-creator",
          "effect": "reads",
          "facts": [
            "Creator association",
            "Execution Accounts"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "reads",
          "facts": [
            "Platform",
            "Username",
            "Profile identity"
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
      "target": "webapp/pages/campaigns.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/campaign_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/pages/campaign-detail.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/campaign_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_creator_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/publication.py"
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

# Missing/ambiguous Campaign refused

## Trigger

Request activity inventory or select activity detail.

## Outcome

Missing or ambiguous conversational campaign identity is refused without selecting an arbitrary campaign.
