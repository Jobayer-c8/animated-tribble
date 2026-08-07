# Bolt's Performance Journal

## 2025-08-07 - Parallelized GitHub API fetching in github-script
**Learning:** Sequential await calls for independent GitHub REST API requests (commits, pulls, issues) introduce significant execution latency as each request must complete before the next begins. Parallelizing them with `Promise.all` can reduce the total script execution time substantially by overlapping HTTP wait times. Additionally, pre-calculating invariant reference timestamps outside of filter callbacks avoids redundant object instantiation and string parsing overhead.
**Action:** Use `Promise.all` for parallel API fetching and pre-calculate reference timestamps whenever modifying or writing new workflow scripts.
