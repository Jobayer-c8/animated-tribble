# Bolt's Performance Journal

This is Bolt's performance journal for critical learnings.

## 2025-02-18 - GitHub API Parallelization and Date Object Optimization
**Learning:** GitHub API calls (like fetching commits, pull requests, and issues) executed sequentially introduce unnecessary idle/network latency times, which can be optimized via parallelization (`Promise.all`). Additionally, repeatedly instantiating reference dates like `new Date(since)` within filter callback loops consumes redundant CPU cycles and memory.
**Action:** Parallelize independent GitHub REST API requests using `Promise.all` and lift invariant objects (like the `since` Date object) out of loop/callback execution context to minimize overhead.
