---
emoji: 📣
description: Daily repository activity report created as an issue
on:
  schedule:
    - cron: '0 9 * * *'
  workflow_dispatch: {}
permissions:
  contents: read
  issues: read
tools:
  github:
    mode: gh-proxy
    toolsets: [default]
safe-outputs:
  create-issue:
---

# Daily Activity Report

## Task

Create a daily report summarizing recent repository activity (last 24 hours):

- commits
- merged pull requests
- newly opened issues

If there is no activity, create a short "No activity" report (do not fail).

## Safe Outputs

- `create-issue`: used to create the report issue when there is new content.

## Report Format

- Title: `Daily activity report — YYYY-MM-DD`
- Body should contain sections starting at `###` headings for `Commits`, `Merged PRs`, and `New Issues`.
- Provide links to commits, PRs, and issues. For long lists, wrap in `<details>` blocks.

## Notes

- The workflow runs on a daily schedule and can be manually triggered via `workflow_dispatch`.
- The agent should run read-only; use the configured `create-issue` safe output for writes.
- Independent GitHub API calls (commits, pull requests, issues) are executed in parallel via `Promise.all` for minimal workflow runtime.
