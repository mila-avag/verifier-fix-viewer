# Verifier-Fix Bundle — Audit Viewer

A single, self-contained HTML viewer for the verifier-quality fix bundle. All data
(rubric edits/deletes, unit-test edits/deletes, the rewritten test files, and every
justification) is baked directly into `index.html` — no server or network needed.

## View it
- **Live (GitHub Pages):** see the repo's Pages URL.
- **Locally:** just open `index.html` in any browser.

## What's inside
| Tab | Contents |
|---|---|
| Overview | The bundle README (file/column docs + how to apply the fixes). |
| Rubric Edits | Old → new rubric diff, flagged issue, and the rewrite justification. |
| Rubric Deletes | Each rubric to remove + the deletion reason. |
| Test Edits | Every edited test, with severity, categories, and reason. |
| Test Deletes | Every deleted test, with severity, categories, and reason. |
| Test Files | The full rewritten `unit_tests/<task_id>.py` files (edits + deletes applied). |

Each tab supports text search; the rubric/test tabs also filter by severity (major/minor).

## Regenerating
This file is produced by `build_rewrite_viewer.py` from a rewrites output dir:

```bash
python build_rewrite_viewer.py \
  --dir outputs/delivery_quality_0620/rewrites_partial \
  --output verifier_fix_viewer/index.html
```

> Note: this viewer embeds task prompts, rubrics, and test code. Treat the published
> page accordingly.
