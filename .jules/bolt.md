## 2025-07-14 - Parallelizing GitHub API Calls in Workflows
**Learning:** Sequential await calls for independent GitHub API requests (like listing commits, PRs, and issues) introduce significant avoidable latency.
**Action:** Use `Promise.all` to parallelize independent `github.rest` calls. Additionally, comparing ISO 8601 date strings directly avoids the overhead of `new Date()` instantiation in filter loops.
