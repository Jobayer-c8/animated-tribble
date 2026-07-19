# Bolt Persistent Performance Journal

This journal tracks critical, high-impact performance learnings, surprising findings, and patterns specific to the codebase.

## 2025-07-19 - Daily Activity Report Performance Bottleneck
**Learning:** Sequential await calls on independent GitHub API endpoints (`listCommits`, `pulls.list`, and `issues.listForRepo`) block execution, adding unnecessary latency. Additionally, converting ISO 8601 strings to Date objects repeatedly inside a `.filter` loop causes redundant garbage collection and overhead.
**Action:** Parallelize independent network calls using `Promise.all` and use direct lexicographical comparison on date strings for temporal filtering.
