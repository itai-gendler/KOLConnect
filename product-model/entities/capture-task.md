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
    }
  ]
}
---

# Capture Task

Ordinary link-based capture work with normalization, execution, retry and library-import outcomes.

## Information kept

- **Task identity** — Addressed capture-work identity.
- **Name** — Task name.
- **Original inputs** — Original supplied links.
- **Normalization results** — Normalization, deduplication and rejected-input results.
- **Platform scope** — Selected platforms.
- **Lifecycle** — Current capture lifecycle.
- **Control requests** — Persisted pause and stop requests.
- **Progress** — Capture progress and diagnostic outcomes.
- **Run summary** — Execution scope, timings, counts and terminal outcome.
- **Artifacts** — Controlled results files and folder.
- **Retry scope** — Selected failed-input retry scope.
- **Library import outcome** — Canonical library-import counts and failures.

## States

### Created

Usable ordinary capture work has been initialized without starting a worker.

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
