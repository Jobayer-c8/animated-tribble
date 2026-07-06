# Bolt's Performance Journal

## 2025-07-06 - Parallelizing GitHub API calls in workflows
**Learning:** Sequential `await` calls for independent GitHub API requests (commits, PRs, issues) in `actions/github-script` workflows unnecessarily increase wall-clock time.
**Action:** Always use `Promise.all` for independent network requests to reduce script execution time in CI environments.
