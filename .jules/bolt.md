## 2025-05-14 - Parallelize GitHub API calls and string-based date comparisons
**Learning:** Sequential network requests in `actions/github-script` workflows are a common bottleneck. Using `Promise.all` can reduce execution time by up to 66% if three independent calls are parallelized. Additionally, comparing ISO 8601 strings directly avoids unnecessary `new Date()` overhead in filter loops.
**Action:** Always check for independent API calls that can be parallelized and prefer string comparison for standardized ISO timestamps.
