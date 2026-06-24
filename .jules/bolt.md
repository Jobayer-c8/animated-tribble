## 2024-06-24 - Parallelize GitHub API calls in daily report
**Learning:** Sequential await calls for `listCommits`, `pulls.list`, and `issues.listForRepo` significantly increase workflow execution time as each call must wait for the previous one to complete.
**Action:** Use `Promise.all` to execute independent GitHub API requests concurrently, reducing total wait time to the duration of the slowest request.

## 2024-06-24 - Pre-calculate date objects for filters
**Learning:** Creating a `new Date()` object inside a `.filter()` or `.map()` callback that iterates over a large array (e.g., 100 items) is redundant and adds unnecessary overhead.
**Action:** Move invariant object creation outside of the loop/callback to improve efficiency.
