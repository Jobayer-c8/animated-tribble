## 2025-05-15 - Optimizing GitHub API calls in Scripts
**Learning:** Sequential await calls for independent GitHub API requests (commits, pulls, issues) significantly increase total execution time. Additionally, instantiating `new Date()` within a filter loop for large datasets introduces unnecessary CPU/memory overhead.
**Action:** Always parallelize independent API calls using `Promise.all`. For ISO-8601 date comparisons, use direct string comparison instead of `new Date()` instantiation where possible.
