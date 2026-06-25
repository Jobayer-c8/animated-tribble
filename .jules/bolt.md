## 2025-05-14 - [Parallelizing API calls in github-script]
**Learning:** GitHub Action workflows using `actions/github-script` often fetch multiple independent data sources (commits, PRs, issues) sequentially. This can be significantly optimized by using `Promise.all` to parallelize these network-bound operations.
**Action:** Always look for independent `await` calls to the GitHub API in workflow scripts and wrap them in `Promise.all` to reduce total execution time.
