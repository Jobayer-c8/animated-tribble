# Bolt's Performance Journal

This is Bolt's performance journal documenting critical, codebase-specific performance patterns and learnings.

## 2025-03-01 - Parallelizing GitHub Action API Requests
**Learning:** Making sequential asynchronous requests within the GitHub Script action blocks the execution path and serializes network delay. For typical repositories, `Promise.all` allows fetching commits, pulls, and issues concurrently, significantly reducing script runtime since network latency is the main bottleneck.
**Action:** Always parallelize independent GitHub API calls (e.g., `listCommits`, `pulls.list`, `issues.listForRepo`) using `Promise.all`.
