---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "detail": "Campaign Detail"
  },
  "steps": [
    {
      "text": "Request permanent deletion of the selected activity.",
      "kind": "actor",
      "actor": "local-user",
      "capability": "delete-campaign",
      "entities": [],
      "contexts": {
        "detail": {
          "place": "kolconnect-desktop::campaign-detail"
        }
      }
    },
    {
      "text": "Delete the selected Campaign and supported dependents, then carry the user to campaign inventory.",
      "kind": "product",
      "actor": "local-user",
      "capability": "delete-campaign",
      "entities": [
        {
          "entity": "campaign",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "campaign-creator",
          "effect": "removes",
          "with": "campaign",
          "from": "Active"
        },
        {
          "entity": "campaign-brief",
          "effect": "removes",
          "with": "campaign"
        },
        {
          "entity": "content-submission",
          "effect": "removes",
          "with": "campaign-creator",
          "from": "Pending"
        },
        {
          "entity": "actual-publication",
          "effect": "removes",
          "with": "campaign-creator"
        }
      ],
      "contexts": {
        "detail": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    },
    {
      "text": "Request the inventory returned after permanent deletion.",
      "kind": "actor",
      "actor": "local-user",
      "capability": "browse-campaigns",
      "entities": [],
      "contexts": {
        "detail": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    },
    {
      "text": "Permanent deletion succeeds and the returned inventory excludes the deleted campaign identity.",
      "kind": "product",
      "actor": "local-user",
      "capability": "browse-campaigns",
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
        "detail": {
          "place": "kolconnect-desktop::campaigns"
        }
      }
    }
  ],
  "references": [
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

# Deleted campaign absent from inventory

## Trigger

Request permanent deletion of the selected activity.

## Outcome

Permanent deletion succeeds and the returned inventory excludes the deleted campaign identity.


## Edge cases

- This case removes Active campaign/participation records and Pending submissions. Archive markers and a different human-review state do not by themselves prevent the same permanent removal.
