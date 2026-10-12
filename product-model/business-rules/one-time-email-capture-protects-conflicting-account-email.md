---
{
  "appliesTo": [
    {
      "type": "capability-scenario",
      "id": "enrich-contact-emails-3-manual-url-updates-existing-identity",
      "contexts": [
        {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      ]
    },
    {
      "type": "capability-scenario",
      "id": "enrich-contact-emails-4-manual-url-creates-identity-without-visible-task",
      "contexts": [
        {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      ]
    },
    {
      "type": "capability-scenario",
      "id": "enrich-contact-emails-7-conflicting-account-email-preserved",
      "contexts": [
        {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      ]
    },
    {
      "type": "entity",
      "id": "creator-account",
      "effect": "changes",
      "facts": [
        "Account email"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      ]
    },
    {
      "type": "entity",
      "id": "creator",
      "effect": "changes",
      "facts": [
        "Name",
        "Contact details"
      ],
      "contexts": [
        {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      ]
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

# One-time email capture protects conflicting Account email

One-time URL email capture preserves an existing conflicting account email. Its supported Creator-level name/contact updates can still occur, so preserved account email does not imply no change anywhere in the profile.
