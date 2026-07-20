# Bolt's Performance Journal

This is a persistent record of performance-related learnings, surprising bottlenecks, or codebase-specific patterns encountered in this repository.

## 2025-02-14 - Parallel API Calls & Efficient Time Comparison in Daily Activity Report
**Learning:** Sequential await calls to the GitHub REST API (`listCommits`, `pulls.list`, `listForRepo`) significantly increase execution duration. Combining them using `Promise.all` allows parallel execution and cuts down total latency. Additionally, parsing date strings via `new Date()` inside a filter callback creates redundant object instantiations; direct lexicographical comparison of ISO 8601 strings is faster and correct for standardized timestamps.
**Action:** Use `Promise.all` for independent REST API fetches and direct ISO string comparison for merged PR temporal filtering.
