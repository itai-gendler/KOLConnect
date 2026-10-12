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
    },
    {
      "type": "capability",
      "id": "browse-campaigns",
      "contexts": [
        {
          "place": "kolconnect-desktop::campaigns"
        },
        {
          "place": "kolconnect-desktop::campaign-detail"
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
      "target": "app/domain/publication.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/risk_service.py#_missing_publish_links"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/risk_service.py#get_risks"
    }
  ]
}
---

# Risk projections use their inspected predicates

A completed participation with empty publication links appears in the missing-publication projection. Its risk is high when a parseable publication date precedes today, otherwise low. This missing-link predicate does not itself exclude archived Campaigns or participations.

The general risk projection marks an Active Creator missing email at medium risk only when neither its own email nor any linked account email is usable; a nonempty address other than the missing-capture sentinel is usable here, without an email-syntax test. An Active Campaign missing Product association or start date has medium data risk. The general projection orders high before medium before low and retains counts for each level.

Workbench action-center missing-email entries instead identify accounts with an empty recorded account email, and its Campaign projection excludes archived Campaigns. These read predicates do not restrict who may mutate a record.
