---
{
  "scope": "Broad pinned-source inspection of Desktop, Chrome Extension and Feishu Chat entry, orchestration, persistence, replication and maintenance code.",
  "method": "Static entry-to-outcome source inspection at 5aa4f5f50d1decd4fc49b84b268526e96e52a231; no target execution.",
  "covered": [
    {
      "description": "Desktop arrival, working-subject controls, settings and product-carried navigation code.",
      "paths": [
        "webapp/",
        "app/launcher.py"
      ]
    },
    {
      "description": "Mapped request dispatch, local request validation, local health checks and application orchestration.",
      "paths": [
        "app/http_handlers/",
        "app/server.py",
        "app/local_request_security.py"
      ]
    },
    {
      "description": "Canonical creator/account identity, capture/review, destructive plans and compatibility persistence.",
      "paths": [
        "app/services/",
        "app/repositories/",
        "app/storage/",
        "app/adapters/",
        "app/creator_repository.py",
        "app/creator_batch_import.py",
        "app/creator_library_export.py",
        "app/task_manager.py"
      ]
    },
    {
      "description": "Campaign/product records, monetary identity, publication normalization and path-specific dashboard time/projection predicates.",
      "paths": [
        "app/campaign_repository.py",
        "app/campaign_creator_repository.py",
        "app/product_repository.py",
        "app/dashboard_service.py",
        "app/dashboard_repository.py",
        "app/domain/"
      ]
    },
    {
      "description": "Bounded mailbox observation and outgoing replication client code.",
      "paths": [
        "app/mail_sync.py",
        "app/feishu_client.py",
        "app/feishu_relation.py",
        "app/google_sheets_client.py"
      ]
    },
    {
      "description": "Supported-page extension collection, analysis sessions, lookup/import callbacks and redacted diagnostics.",
      "paths": [
        "chrome_extension/"
      ]
    },
    {
      "description": "Exposed runtime recording and controlled desktop artifacts.",
      "paths": [
        "app/app_logging.py",
        "app/desktop_file_bridge.py",
        "app/runtime_paths.py"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Test harnesses and fixtures.",
      "paths": [
        "tests/",
        "chrome_extension/tests/"
      ]
    },
    {
      "description": "Packaging, build/release, CI and standalone engineering generators.",
      "paths": [
        "packaging/",
        "scripts/",
        ".github/"
      ]
    },
    {
      "description": "Artwork, styling and vendored presentation dependencies.",
      "paths": [
        "assets/",
        "chrome_extension/icons/",
        "webapp/styles.css",
        "chrome_extension/content/floating_assistant.css",
        "webapp/vendor/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Full remote deletion reconciliation, retries and startup scheduling beyond mapped local deletion outcomes.",
      "paths": [
        "app/services/feishu_delete_intent_service.py",
        "app/http_handlers/feishu_delete_handler.py",
        "app/staged_delete_transaction.py",
        "app/server.py"
      ]
    },
    {
      "description": "Backend-only Sent synchronization arrival and complete workflow beyond the inspected queue-clearing predicate.",
      "paths": [
        "app/http_handlers/settings_handler.py",
        "app/mail_sync.py",
        "app/services/mail_inbox_facts.py"
      ]
    },
    {
      "description": "Independent campaign-execution workspace arrival beyond embedded campaign-detail execution.",
      "paths": [
        "webapp/pages/campaign-execution.js"
      ]
    },
    {
      "description": "Exhaustive platform browser recovery, standalone scraper command and legacy integration modes.",
      "paths": [
        "app/scraper.py"
      ]
    },
    {
      "description": "Exhaustive compatibility/SQLite parity, schema-upgrade failures, dependent cleanup and migration corner cases.",
      "paths": [
        "app/storage/",
        "app/creator_data_compat.py",
        "app/excel_workbook_store.py",
        "app/repository_factory.py"
      ]
    },
    {
      "description": "Backend-only profile/follower edits, direct manual-task/Agency creation and unoffered participation/archive relation mutations.",
      "paths": [
        "app/http_handlers/creator_handler.py",
        "app/services/creator_service.py",
        "app/services/agency_service.py",
        "app/adapters/task_manager_adapter.py",
        "app/http_handlers/campaign_handler.py",
        "app/campaign_creator_repository.py"
      ]
    },
    {
      "description": "Legacy FollowUpLogs production/disclosure and external Contact-import contracts.",
      "paths": [
        "app/creator_repository.py",
        "app/services/agency_service.py"
      ]
    },
    {
      "description": "Injected successful metric/AI provider flows and provider-backed similarity explanation offerings.",
      "paths": [
        "app/services/publication_tracking_service.py",
        "app/services/assistant_provider.py",
        "app/services/similarity_explanation.py"
      ]
    },
    {
      "description": "Remaining archive/stage predicate parity across untraced mutation and projection paths.",
      "paths": [
        "app/services/campaign_execution_service.py",
        "app/campaign_creator_repository.py",
        "app/dashboard_service.py",
        "app/services/mail_follow_up.py"
      ]
    },
    {
      "description": "Schema-6 reset effects for native mail facts/preferences and historical metric observations beyond the inspected compatibility clear.",
      "paths": [
        "app/services/clean_reset_service.py",
        "app/storage/sqlite_workbook_store.py",
        "app/storage/schema.py"
      ]
    }
  ],
  "limitations": [
    {
      "description": "TikTok documentation and wired collector deployment classification remain contradictory; source-specific collection bounds are inspected.",
      "paths": [
        "README.md",
        "chrome_extension/manifest.json",
        "chrome_extension/capture/",
        "chrome_extension/core/content_analysis.js",
        "app/server.py"
      ]
    }
  ]
}
---

# Coverage


