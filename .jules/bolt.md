## 2025-05-14 - Parallel API Fetching in GitHub Scripts
**Learning:** Parallelizing independent GitHub API calls using 'Promise.all' in 'actions/github-script' significantly reduces workflow execution time. Direct string comparison for ISO 8601 dates (e.g., 'p.merged_at >= since') is more efficient than instantiating 'new Date()' objects inside filter loops.
**Action:** Always look for sequential 'await' calls on independent data fetching in scripts and parallelize them. Prefer lexicographical string comparison for standardized timestamps.
