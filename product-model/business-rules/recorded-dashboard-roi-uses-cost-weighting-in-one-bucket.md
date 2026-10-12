---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-workbench",
      "contexts": [
        {
          "place": "kolconnect-desktop::workbench"
        },
        {
          "place": "feishu-chat-assistant"
        }
      ]
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/dashboard_service.py#_weighted_completed_roi"
    }
  ]
}
---

# Recorded dashboard ROI uses cost weighting in one bucket

Dashboard recorded ROI is cost-weighted for completed nonarchived cooperation with finite positive cost and finite nonnegative recorded ROI in one compatible currency bucket. Multiple buckets are unavailable; no eligible total returns zero.
