## 2025-05-14 - Parallelize independent GitHub API calls
**Learning:** In GitHub Agentic Workflows (gh-aw), scripts often perform multiple independent API calls sequentially. Parallelizing these with Promise.all reduces the total execution time of the workflow significantly.
**Action:** Always check for independent 'await' calls to the GitHub API and wrap them in Promise.all where possible.
