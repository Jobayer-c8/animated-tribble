# Bolt's Performance Journal

## 2025-02-18 - GitHub API Date String Comparison trap
**Learning:** In GitHub Action workflows using `actions/github-script`, comparing ISO 8601 date strings directly (e.g., `p.merged_at >= since`) fails lexicographically if one string has millisecond precision (JS `.toISOString()`) and the other does not (GitHub API `merged_at`), because 'Z' (ASCII 90) is lexicographically greater than '.' (ASCII 46). Always use `new Date()` instantiation to guarantee correct chronological comparison.
**Action:** When comparing dates from API payloads, instantiate `new Date()` once outside loop/filter callbacks to optimize processing while avoiding lexicographical comparison issues.
