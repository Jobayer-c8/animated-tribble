## 2025-05-14 - Parallelizing GitHub API calls in workflows
**Learning:** GitHub Action scripts using `actions/github-script` often fetch data serially. Parallelizing independent API calls (e.g., commits, pulls, issues) using `Promise.all` can significantly reduce the workflow's "wall clock" time by overlapping I/O wait.
**Action:** Always check for independent `await` calls in I/O bound scripts and parallelize them where possible.
