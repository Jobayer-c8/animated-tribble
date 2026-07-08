## 2025-05-14 - Parallelizing GitHub API Calls
**Learning:** Independent GitHub API calls in `actions/github-script` can be significantly optimized using `Promise.all`. However, note that `github.rest.pulls.list` lacks a `since` parameter, unlike `repos.listCommits`, necessitating client-side filtering which can be further optimized by pre-calculating Date objects.
**Action:** Always check for `since` parameter support in GitHub REST API methods and parallelize independent fetches.
