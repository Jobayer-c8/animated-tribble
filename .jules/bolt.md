## 2025-05-14 - Parallel API Fetching in GitHub Scripts
**Learning:** Sequential `await` calls for independent GitHub API requests (commits, PRs, issues) in `actions/github-script` introduce unnecessary latency proportional to the number of calls.
**Action:** Use `Promise.all` to parallelize I/O-bound GitHub API requests to reduce workflow execution time.

## 2025-05-14 - ISO String Date Comparison
**Learning:** Instantiating `new Date()` objects inside filter loops for comparing ISO 8601 timestamps is expensive and redundant. ISO 8601 strings are lexicographically sortable.
**Action:** Compare ISO 8601 date strings directly (e.g., `p.merged_at >= since`) to avoid object instantiation overhead in loops.
