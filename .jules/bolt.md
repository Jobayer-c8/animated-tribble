# Bolt's Performance Journal

## 2025-03-01 - Parallelizing Workflow API Calls & Hoisting Invariant Date Object Instantiation
**Learning:** Sequential GitHub API calls (`github.rest.repos.listCommits`, `github.rest.pulls.list`, and `github.rest.issues.listForRepo`) within a GitHub Action script run on 'ubuntu-latest' incur significant network round-trip overhead. Parallelizing them via `Promise.all` slashes total network/script execution time. In addition, hoisting invariant object instantiations (such as the reference `sinceDate` Date object) outside of array filter callbacks prevents redundant CPU-intensive object allocations and garbage collection overhead during large page iterations.
**Action:** When working with GitHub Action workflow scripts or Node-based API utilities, always parallelize independent requests via `Promise.all` and ensure invariant calculations or object creations are hoisted out of array filter or map loops.
