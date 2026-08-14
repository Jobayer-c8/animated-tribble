# Bolt's Performance Journal

This is Bolt's performance journal for this project, tracking critical learnings, surprising bottlenecks, or codebase-specific patterns.

## 2025-02-18 - Parallelizing GitHub API Calls in Workflows
**Learning:** Sequential awaits on GitHub REST API calls (e.g., `listCommits`, `pulls.list`, `issues.listForRepo`) introduce unnecessary sequential latency due to network round-trips. Since these queries are independent, they can be fired concurrently using `Promise.all`. Additionally, pre-calculating `since` Date objects outside the array filter callback avoids redundant object instantiation overhead inside iteration loops.
**Action:** Always fetch independent API data collections in parallel via `Promise.all` and hoist static/invariant calculations out of filter/map loops in GitHub script actions.
