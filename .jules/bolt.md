## 2025-05-15 - Parallelizing GitHub API Calls in workflows
**Learning:** Sequential `await` calls for independent GitHub API resources (commits, PRs, issues) in `actions/github-script` introduce unnecessary latency. Parallelizing them with `Promise.all` reduces execution time to the slowest request.
**Action:** Always look for independent API calls in workflow scripts and parallelize them.

## 2025-05-15 - Redundant Object Creation in Loops
**Learning:** Creating a `new Date()` or parsing a timestamp string inside a `.filter()` or `.map()` loop is an O(n) overhead that can be avoided by pre-calculating the reference date outside the loop.
**Action:** Move invariant object/value calculations outside of iteration callbacks.
