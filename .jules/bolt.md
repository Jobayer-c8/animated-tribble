# Bolt's Performance Journal

This is a persistent performance journal to track critical learnings, codebase-specific patterns, and optimization insights.

## 2025-03-01 - Parallelize GitHub API and Pre-calculate Invariants
**Learning:** Sequential GitHub API calls inside GitHub Actions scripts slow down total workflow execution due to network latency, which can be significantly reduced by parallelizing non-dependent requests using `Promise.all()`. Additionally, creating `new Date()` instances inside loops or array filters like `.filter()` creates unnecessary object allocations and redundant calculations. Pre-calculating comparison reference dates outside filter callbacks avoids this overhead.
**Action:** Use `Promise.all()` to fire off sequential API queries concurrently, and instantiate any comparison date objects once outside filter callbacks.
