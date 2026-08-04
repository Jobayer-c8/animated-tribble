## 2025-08-04 - Parallel API Fetching in GitHub Script
**Learning:** Sequential await calls for `listCommits`, `pulls.list`, and `listForRepo` in actions/github-script workflows introduce unnecessary latency by waiting for each API call to resolve before starting the next.
**Action:** Use Promise.all() to run independent GitHub API requests concurrently, and pre-calculate any invariant date references outside of loops/filter callbacks to optimize script efficiency.
