## 2025-05-14 - Parallelized API calls and optimized date filtering
**Learning:** Sequential GitHub API calls in workflows can be significantly slow. Parallelizing them with `Promise.all` reduces execution time to the duration of the longest call. Additionally, creating `Date` objects inside a `filter` or `map` loop is an anti-pattern that adds unnecessary overhead.
**Action:** Always check for independent `await` calls and consider `Promise.all`. Pre-calculate constants or invariant objects before entering loops or filter callbacks.
