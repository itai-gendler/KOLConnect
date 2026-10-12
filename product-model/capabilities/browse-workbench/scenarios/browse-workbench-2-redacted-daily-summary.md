---
{
  "kind": "primary",
  "routes": {
    "offered": "Feishu Chat"
  },
  "steps": [
    {
      "text": "Ask for the workbench metrics or the daily summary.",
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
      "text": "Chat returns Creator total and recent-new count, sourcing/running Campaign count and exact pending/running/failed task-status counts.",
      "kind": "product",
      "actor": "feishu-chat-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "reads",
          "facts": [
            "Identity",
            "Creation time"
          ]
        },
        {
          "entity": "campaign",
          "effect": "reads",
          "facts": [
            "Identity",
            "Business status"
          ]
        },
        {
          "entity": "capture-task",
          "effect": "reads",
          "facts": [
            "Lifecycle"
          ]
        },
        {
          "entity": "manual-task",
          "effect": "reads",
          "facts": [
            "Lifecycle"
          ]
        },
        {
          "entity": "email-recheck-task",
          "effect": "reads",
          "facts": [
            "Lifecycle"
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
          "entity": "campaign-creator",
          "effect": "reads",
          "facts": [
            "Participation identity",
            "Campaign association",
            "Creator association",
            "Execution Accounts",
            "Cooperation stage",
            "Quote currency",
            "Quote unit amount",
            "Quote quantity",
            "Pricing unit",
            "Quote total",
            "Cost",
            "Cost currency",
            "Planned publication dates",
            "Compatibility publication facts",
            "Recorded metrics",
            "Recorded ROI",
            "Performance notes",
            "Responsibility",
            "Next action",
            "Due date",
            "Waiting on",
            "Decision needed",
            "Last progress time",
            "Archive time"
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
      "target": "webapp/pages/dashboard.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/dashboard_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/campaign_execution_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/risk_service.py"
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

# Redacted daily summary

## Trigger

Ask for the workbench metrics or the daily summary.

## Outcome

Chat returns Creator total and recent-new count, sourcing/running Campaign count and exact pending/running/failed task-status counts. The labels do not turn Created, Manual created or Email recheck created into Pending.
