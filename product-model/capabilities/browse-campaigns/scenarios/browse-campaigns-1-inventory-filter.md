---
{
  "kind": "primary",
  "routes": {
    "offered": "Campaigns"
  },
  "steps": [
    {
      "text": "Request activity inventory or select activity detail.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    },
    {
      "text": "Inventory filters return campaign profiles, product association, business status and archive state.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "campaign",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Product association",
            "Country",
            "Target platforms",
            "Start date",
            "End date",
            "Descriptive owner",
            "Budget",
            "Goal",
            "Notes",
            "Business status",
            "Archive time"
          ]
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Company",
            "Notes",
            "Creation time",
            "Update time",
            "Archive time"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::campaigns"
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

# Inventory/filter

## Trigger

Request activity inventory or select activity detail.

## Outcome

Inventory filters return campaign profiles, product association, business status and archive state.
