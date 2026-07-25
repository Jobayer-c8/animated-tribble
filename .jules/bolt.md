# Bolt Performance Journal

This journal tracks critical learnings and optimizations made in this repository.

## 2025-07-25 - Parallelization of GitHub Actions API calls
**Learning:** Standard network operations to GitHub APIs (like `listCommits`, `pulls.list`, and `listForRepo`) in GitHub Script workflow runners run sequentially by default, accumulating high network latency overhead. Wrapping independent API calls in `Promise.all` dramatically decreases workflow execution time.
**Action:** Always group independent GitHub script API fetches in `Promise.all`.
