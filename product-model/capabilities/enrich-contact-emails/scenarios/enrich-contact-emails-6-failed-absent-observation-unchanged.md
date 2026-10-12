---
{
  "kind": "edge",
  "routes": {
    "offered": "Contact Email Enrichment"
  },
  "steps": [
    {
      "text": "Choose library, review-source or manual URL enrichment and its eligible scope.",
      "kind": "actor",
      "actor": "local-user",
      "entities": [],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      }
    },
    {
      "text": "Failed capture or absent email observation leaves existing email unchanged and discloses the observation outcome.",
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
          "entity": "task-result",
          "effect": "reads",
          "facts": [
            "Task/account identity",
            "Capture facts",
            "Capture status",
            "Capture error",
            "Confirmed edits",
            "Review decision",
            "Review reason",
            "Review time",
            "Creator import linkage",
            "Account import linkage"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js#openReviewEmailEnrichment"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/email_url_capture_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/domain/creator_url_resolver.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/creator_service.py#import_url_email_capture"
    },
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
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_result_mapper.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    }
  ]
}
---

# Failed/absent observation unchanged

## Trigger

Choose library, review-source or manual URL enrichment and its eligible scope.

## Outcome

Failed capture or absent email observation leaves existing email unchanged and discloses the observation outcome.
