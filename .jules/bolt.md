## 2026-07-10 - Parallelize GitHub API calls and ISO string comparison
**Learning:** Sequential await calls for independent GitHub REST API requests (e.g., fetching commits, PRs, and issues) multiply total latency. Also, `github.rest.pulls.list` lacks a 'since' parameter, requiring client-side filtering.
**Action:** Use `Promise.all` to fetch independent data concurrently and leverage direct ISO 8601 string comparison for filtering to avoid `new Date()` overhead.
