# PR14 Technical Extraction Handoff

## Purpose

This note preserves the capstone-critical technical follow-on work that was extracted from closed PR #14 into two facilitator-led draft PRs near course closeout.

The goal is to keep the engineering intent, validation evidence, and restart path visible for future contributors without leaving oversized or ambiguous implementation branches hanging open after the course ended.

## Why PR #14 Was Not Merged As-Is

PR #14 combined several different categories of work into one review surface:

- backend DuckDB/data-contract changes
- a new local V2 Streamlit dashboard
- notebook rerun and generated-output churn
- planning and governance discussion
- operator-path and dependency updates

That mixed packaging made the PR harder to review and riskier to merge late in the capstone, even though the dashboard direction itself was aligned with class guidance and received positive feedback during the April 9 review.

## Facilitator-Led Extraction Path

Two smaller draft PRs were opened to preserve the capstone-critical subset from PR #14.

### PR #24: V2 dashboard support views

PR: `feat(workbench): add V2 dashboard support views`

Scope:

- extends `scripts/build_duckdb_baseline.py` with stage-10 exposure/vulnerability ingestion
- extends `scripts/build_duckdb_baseline.py` with stage-20 hazard ingestion
- adds analytical support views for a future V2 dashboard:
  - `vw_index_components`
  - `vw_hazard_breakdown`
  - `vw_vulnerability_breakdown`
  - `vw_vulnerability_factor_summary`
  - `vw_priority_ranking`
- updates `sql/duckdb_baseline_queries.sql`
- extends `tests/test_local_prototype_baseline.py`

Validation run:

- `PYTHONPATH=. .venv/bin/pytest -q tests/test_local_prototype_baseline.py`

Recorded result at time of extraction:

- `2 passed`

Reason this slice was separated:

- the V2 dashboard should not land before the backend views and baseline data contract it depends on are understood and validated

### PR #25: V2 Streamlit dashboard path

PR: `feat(workbench): add V2 Streamlit dashboard path`

Scope:

- adds `app/streamlit_app_v2.py`
- adds `plotly` to `requirements.txt`
- extends `run.sh` with V2 launch paths:
  - `./run.sh up-v2`
  - `./run.sh start-v2`
- updates the `README.md` launch notes
- extends `tests/test_local_prototype_baseline.py` with a V2 startup smoke test

Validation run:

- `.venv/bin/pip install -r requirements.txt`
- `PYTHONPATH=. .venv/bin/pytest -q tests/test_local_prototype_baseline.py`
- `bash -n run.sh`

Recorded results at time of extraction:

- `3 passed`
- `run.sh` shell syntax check passed

Reason this slice was stacked:

- the V2 dashboard depends on the support views introduced in PR #24

## Why These Draft PRs Remained Unmerged

These technical slices were preserved but not merged during course closeout because:

- the course had already shifted into archive/handoff mode
- the current public-facing dashboard path was already stable
- the local workbench baseline was already functional without the V2 path
- merging a new backend contract and a second dashboard path after the course ended would have added handoff ambiguity instead of reducing it

In short: the work was meaningful, but no longer necessary for a clean capstone finish.

## What Future Teams Should Do If They Want To Revive This Work

1. Review PR #24 first and decide whether the added DuckDB support views still match the current baseline outputs.
2. Re-run the baseline build and `tests/test_local_prototype_baseline.py` against the current data products.
3. Only after that, review PR #25 and decide whether a separate V2 Streamlit app is still worth keeping.
4. If revived, prefer rebasing or cherry-picking the focused commits into fresh PRs instead of reopening the original course-closeout drafts blindly.

## Closeout Decision

At the end of the Spring 2026 course, the recommended archival position is:

- keep this note as the durable handoff artifact
- close PR #24 and PR #25 with a pointer to this note
- delete the stale remote branches after closure

That preserves the useful technical breadcrumbs without leaving unfinished implementation paths to confuse future maintainers.
