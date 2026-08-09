# Bolt's Performance Journal

This is Bolt's persistent performance journal, recording critical learnings, bottlenecks, and optimizations specific to this codebase's architecture.

## 2025-03-04 - GitHub API Parallelization and Pre-calculation in Activity Report
**Learning:** Sequential GitHub API calls (`listCommits`, `pulls.list`, `issues.listForRepo`) block each other unnecessarily. Using `Promise.all` allows parallel execution and significantly speeds up workflow execution. Additionally, instantiating `new Date(since)` inside `pulls.filter` repeatedly recreates identical `Date` objects, which is inefficient. Pre-calculating it outside of filter/map routines eliminates redundant allocations.
**Action:** Parallelize independent GitHub API calls and pre-calculate any invariant loop values (like Date comparisons) outside of loops/filters.
