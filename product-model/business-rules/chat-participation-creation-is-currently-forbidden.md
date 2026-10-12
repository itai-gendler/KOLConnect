---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "campaign-creator",
      "effect": "creates",
      "contexts": [
        {
          "place": "feishu-chat-assistant"
        }
      ]
    }
  ],
  "permits": [],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/assistant_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/assistant_intent_router.py"
    }
  ]
}
---

# Chat participation creation is currently forbidden

The deferred Chat campaign-addition operation cannot create Campaign Creator participation. This direct creation at Feishu Chat remains forbidden while other confirmed Chat operations keep their separate contracts.
