---
{
  "kind": "primary",
  "routes": {
    "offered": "Workbench"
  },
  "steps": [
    {
      "text": "Ask for the workbench metrics or the daily summary.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::workbench"
        }
      }
    },
    {
      "text": "The workbench returns canonical/account health, currency-separated campaign metrics, cost-weighted recorded ROI and due-action/risk projections without changing those records.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
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
        },
        {
          "entity": "legacy-cooperation",
          "effect": "reads",
          "facts": [
            "Historical identity",
            "Creator association",
            "Campaign description",
            "Platform",
            "Contact date",
            "Untyped price",
            "Publication count",
            "Recorded views",
            "Recorded ROI",
            "Result",
            "Notes",
            "Creation time"
          ]
        },
        {
          "entity": "content-submission",
          "effect": "reads",
          "facts": [
            "Submission identity",
            "Cooperation association",
            "Optional Account",
            "Content type",
            "Content reference",
            "Submission time",
            "Submitted by",
            "Source",
            "Human review",
            "Review note",
            "First-pass findings"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::workbench"
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

# Metrics/actions/risks

## Trigger

Ask for the workbench metrics or the daily summary.

## Outcome

The workbench returns canonical/account health, currency-separated campaign metrics, cost-weighted recorded ROI and due-action/risk projections without changing those records.
