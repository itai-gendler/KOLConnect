---
{
  "entities": [
    {
      "entity": "creator",
      "shows": [
        "Identity",
        "Name",
        "Contact details"
      ]
    },
    {
      "entity": "creator-account",
      "shows": [
        "Canonical identity",
        "Platform",
        "Profile identity",
        "Account email",
        "Creator association"
      ]
    },
    {
      "entity": "email-recheck-task",
      "shows": [
        "Task identity",
        "Name",
        "Candidate source",
        "Source-task/library scope",
        "Candidate Accounts",
        "Email scope",
        "Platform selection",
        "Lifecycle",
        "Email progress",
        "Run summary",
        "Artifacts",
        "Import outcome"
      ],
      "collects": [
        "Candidate source",
        "Source-task/library scope",
        "Candidate Accounts",
        "Email scope",
        "Platform selection"
      ]
    },
    {
      "entity": "task-result",
      "shows": [
        "Task/account identity",
        "Capture facts",
        "Capture status",
        "Creator import linkage",
        "Account import linkage"
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
    }
  ]
}
---

# Contact Email Enrichment

Candidate source, review-task/library scope, identity resolution, email observations and conflict outcomes

 URLs, source and enrichment scope.
