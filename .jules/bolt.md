## 2026-06-21 - [Parallelizing GitHub API calls in Workflows]
**Learning:** Sequential `await` calls in `actions/github-script` can significantly slow down workflows when multiple independent data sets (commits, PRs, issues) are needed. Using `Promise.all` allows these requests to be handled concurrently by the GitHub API.
**Action:** Always check if multiple `github.rest` calls can be parallelized using `Promise.all`.
