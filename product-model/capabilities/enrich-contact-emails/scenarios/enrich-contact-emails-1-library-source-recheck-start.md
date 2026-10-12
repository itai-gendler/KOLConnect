---
{
  "kind": "primary",
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
      "text": "Resolved library candidates initialize a visible email-recheck task, start the selected scope and apply eligible observed email/capture updates.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "creates",
          "facts": [
            "Task identity",
            "Name",
            "Original inputs",
            "Candidate source",
            "Source-task/library scope",
            "Candidate Accounts",
            "Email scope",
            "Platform selection",
            "Lifecycle",
            "Control requests",
            "Email progress",
            "Run summary",
            "Artifacts",
            "Import outcome",
            "Retry scope"
          ],
          "to": "Email recheck created"
        },
        {
          "entity": "task-result",
          "effect": "creates",
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
          ],
          "to": "Pending",
          "with": "email-recheck-task"
        },
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
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      }
    },
    {
      "text": "Start the resolved email-recheck scope with one worker.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Email progress",
            "Run summary"
          ],
          "from": "Email recheck created",
          "to": "Running"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      }
    },
    {
      "text": "Finish the selected capture scope and enter protected finalization.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Run summary",
            "Artifacts"
          ],
          "from": "Running",
          "to": "Finalizing"
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      }
    },
    {
      "text": "For eligible observed candidates, apply supported canonical profile/account updates and retain source capture; conflicting account email stays protected.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "creator",
          "effect": "changes",
          "facts": [
            "Name",
            "Contact details",
            "Update time"
          ]
        },
        {
          "entity": "creator-account",
          "effect": "changes",
          "facts": [
            "Account email",
            "Capture status",
            "Capture time",
            "Source"
          ]
        },
        {
          "entity": "creator-snapshot",
          "effect": "creates",
          "facts": [
            "Capture identity",
            "Source task",
            "Creator association",
            "Observed account",
            "Observed metrics",
            "Score",
            "Level",
            "Capture time",
            "Source"
          ]
        }
      ],
      "contexts": {
        "offered": {
          "place": "kolconnect-desktop::contact-email-enrichment"
        }
      }
    },
    {
      "text": "Finalization and eligible canonical import complete with the selected work's type-specific outcome.",
      "kind": "product",
      "actor": "local-user",
      "entities": [
        {
          "entity": "email-recheck-task",
          "effect": "changes",
          "facts": [
            "Lifecycle",
            "Email progress",
            "Run summary",
            "Import outcome"
          ],
          "from": "Finalizing",
          "to": "Completed"
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

# Library-source recheck/start

## Trigger

Choose library, review-source or manual URL enrichment and its eligible scope.

## Outcome

Resolved library candidates initialize a visible email-recheck task, start the selected scope and apply eligible observed email/capture updates.
