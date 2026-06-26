# Bolt's Journal - Critical Performance Learnings

## 2025-05-14 - Parallelize independent GitHub API calls
**Learning:** Sequential await calls for independent GitHub API data fetching (commits, PRs, issues) can be significantly slower than parallel execution.
**Action:** Use `Promise.all()` to fetch data in parallel when the requests do not depend on each other.

## 2025-05-14 - Pre-calculate invariant values outside loops
**Learning:** Re-parsing the same date string into a Date object inside a filter loop (e.g., for 100 PRs) is wasteful.
**Action:** Instantiate invariant objects or values outside of loops and filter callbacks to minimize redundant operations.
