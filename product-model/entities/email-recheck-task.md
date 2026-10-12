---
{
  "domain": "email-crawl",
  "relations": [
    {
      "entity": "task-result",
      "verb": "contains",
      "cardinality": "one-to-many"
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

# Email Recheck Task

An addressed email-recheck task whose candidates come from library or review-task scope.

## Information kept

- **Original inputs** — Original retained input links addressed by task add/edit/remove/copy controls.
- **Control requests** — Persisted pause and stop requests for this task family.
- **Task identity** — Addressed email-recheck identity.
- **Name** — Task name.
- **Candidate source** — Library or review-task candidate source.
- **Source-task/library scope** — Selected source task or canonical-library scope.
- **Candidate Accounts** — Resolved candidate account identities.
- **Email scope** — Selected email-enrichment scope.
- **Platform selection** — Platforms selected for enrichment.
- **Lifecycle** — Current email-recheck lifecycle.
- **Email progress** — Per-account enrichment progress and outcomes.
- **Run summary** — Execution scope, timing and terminal outcome.
- **Artifacts** — Controlled recheck artifacts.
- **Import outcome** — Canonical import and email update outcome.

- **Retry scope** — Selected failed-input retry links, round and request information retained by shared retry preparation.

## States

### Email recheck created

Resolved email-recheck scope has been initialized; execution has not started.

### Created

Failed-input retry has reset this existing task family's preparation lifecycle; this is not its initial initialization state.

### Running

The selected work has a running worker.

### Paused

The live worker has reached the pause boundary.

### Interrupted

Work was running but no worker remains; it can be continued where eligible.

### Stopping

Stopping has been requested while a worker remains.

### Stopped

The worker has stopped, or eligible workerless work was stopped directly.

### Finalizing

Capture is complete enough to finalize results and canonical import; concurrent control/mutation is protected.

### Completed

Finalization and supported canonical import have completed.

### Failed

Execution or finalization/import failed and the failure is disclosed.
