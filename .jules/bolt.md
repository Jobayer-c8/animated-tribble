## 2025-03-02 - Parallelization and Date Comparison in GitHub Script Workflow
**Learning:** For workflows running via `actions/github-script` or `gh-aw`, parallelizing independent API requests with `Promise.all` dramatically decreases the total duration of the runner step. Additionally, comparing ISO date strings lexicographically is faster and less memory-intensive than parsing dates with `new Date()` inside iteration loops.
**Action:** Always parallelize independent Octokit API calls, and use direct string comparisons for ISO 8601 timestamps inside high-frequency filters.
