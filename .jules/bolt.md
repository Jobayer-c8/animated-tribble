## 2025-05-22 - Parallelize GitHub API calls in workflows
**Learning:** Sequential API calls in GitHub Action scripts using `actions/github-script` introduce unnecessary latency due to multiple round-trip times (RTT).
**Action:** Use `Promise.all` to parallelize independent data-gathering API calls to reduce total execution time to a single RTT.
