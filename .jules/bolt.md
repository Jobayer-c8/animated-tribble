## 2025-05-15 - Parallelizing GitHub API calls in workflows
**Learning:** Sequential await calls in `actions/github-script` for independent data (commits, PRs, issues) create an unnecessary bottleneck.
**Action:** Use `Promise.all` to fetch repository activity data in parallel.

## 2025-05-15 - ISO 8601 String Comparison
**Learning:** For chronological comparisons of ISO 8601 strings from GitHub API, direct string comparison (`p.merged_at >= since`) is lexicographically correct and more efficient than instantiating `new Date()` objects.
**Action:** Prefer string comparison for performance-critical filter loops in scripts.
