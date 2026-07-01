## 2025-05-14 - Parallelize GitHub API calls in workflows
**Learning:** Sequential `await` calls for independent GitHub API data fetching are a common bottleneck in workflow scripts. Parallelizing them with `Promise.all` can significantly reduce the total execution time of the action.
**Action:** Always check for independent `await` calls in `actions/github-script` steps and parallelize them where possible.
