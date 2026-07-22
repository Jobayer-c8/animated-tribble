# Bolt's Performance Journal

This journal tracks critical performance learnings, bottlenecks, and optimization observations specific to this repository.

## 2025-03-02 - Parallel Fetching and Pre-computation in Activity Report
**Learning:** Sequential await calls to separate, independent endpoints like GitHub's listCommits, pulls.list, and issues.listForRepo introduce unnecessary latency equivalent to the sum of the request times. Pre-parsing invariant Date objects prevents redundant string-to-date instantiation overhead inside filters.
**Action:** Use `Promise.all` to parallelize independent API requests and pre-parse the `since` threshold into a millisecond timestamp comparison outside of loops.
