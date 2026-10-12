---
{
  "appliesTo": [
    {
      "type": "context",
      "context": {
        "place": "feishu-chat-assistant"
      }
    }
  ],
  "references": [
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/feishu_chat_service.py#_render_success"
    }
  ]
}
---

# Chat disclosure and operations stay within the shipped allowlist

Chat discloses bounded redacted creator/campaign/task/daily/preview reads and offers confirmed task creation/full Feishu sync. Other requested operations are unavailable; it does not imply Desktop parity.

The daily reply exposes Creator total/recent-new count, Campaign count for sourcing/running status, and exact persisted pending/running/failed task counts. It does not classify Created, Manual created or Email recheck created as Pending, and that Campaign counter does not add a universal archive predicate.

Creator search replies expand at most ten matches with name, platform, available followers and country. Creator detail adds available account handles/profile addresses and language. Campaign lists expand at most ten entries with name, status and Product name; detail adds target platforms, country and at most ten distinct Creators with their execution-account labels. Task replies show addressed name/identity, exact lifecycle and available success/failure counts. Synchronization previews expose create/update/relation/conflict counts. These replies do not disclose credentials, correspondence bodies, contact addresses or commercial amounts.
