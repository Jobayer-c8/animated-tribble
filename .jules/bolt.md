## 2025-05-15 - Parallelize API calls in Daily Activity Report
**Learning:** Sequential await calls for independent GitHub API requests increase total execution time. Using `Promise.all` allows these requests to be handled concurrently by the GitHub API.
**Action:** Always check for independent API calls that can be parallelized. Pre-calculate invariant objects outside of loops to minimize redundant operations.
