## 2025-05-22 - Parallelizing GitHub API calls in workflows
**Learning:** Sequential `await` calls for independent GitHub API requests in `actions/github-script` introduce unnecessary latency that can be easily eliminated with `Promise.all`.
**Action:** Always look for independent API calls in workflows and parallelize them. Pre-calculating invariant data (like reference dates) outside of loops/filters further optimizes execution.
