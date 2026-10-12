---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "start-task",
      "contexts": [
        {
          "place": "kolconnect-desktop::capture-tasks"
        }
      ]
    },
    {
      "type": "capability",
      "id": "enrich-contact-emails",
      "contexts": [
        {
          "place": "kolconnect-desktop::contact-email-enrichment"
        },
        {
          "place": "kolconnect-desktop::workbench"
        },
        {
          "place": "kolconnect-desktop::review-results"
        }
      ]
    },
    {
      "type": "capability",
      "id": "analyze-profile",
      "contexts": [
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    },
    {
      "type": "capability",
      "id": "analyze-recent-content",
      "contexts": [
        {
          "place": "kolconnect-chrome-extension::creator-account-capture"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webapp/app.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/http_handlers/task_handler.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/services/task_service.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/adapters/task_manager_adapter.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/repositories/task_repository.py"
    },
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
      "target": "app/services/task_result_mapper.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/creator_repository.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/content/floating_assistant.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/analysis_session.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/content_analysis.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/core/diagnostics.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/services/local_api.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "app/server.py#import_extension_capture"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/platform/instagram.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/platform/youtube.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/capture/tiktok_capture_session.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chrome_extension/content/tiktok_capture_runtime.js"
    }
  ]
}
---

# Unobserved capture metrics remain unavailable

Missing or unobserved capture facts remain unavailable. An ambiguous legacy flat zero is not a guaranteed observed zero; qualified analysis and stored captures must not fabricate complete measurements.
