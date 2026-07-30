# Bolt's Performance Journal

## 2025-02-15 - Parallelizing Independent API Calls in GitHub Actions
**Learning:** In workflows powered by `actions/github-script`, making successive sequential await calls to standard GitHub endpoints (like listing commits, pull requests, and issues) scales the run duration linearly with the sum of all network roundtrip times.
**Action:** Always parallelize independent REST API fetches with `Promise.all` to overlap network latencies, and hoist invariant Date instance calculations out of iterators to minimize memory/CPU allocations.
