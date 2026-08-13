# Bolt's Performance Journal

This is a persistent log of critical performance learnings.

## 2025-02-17 - Date Comparison Performance Trap
**Learning:** Comparing ISO 8601 date strings directly (e.g., `p.merged_at >= since`) fails lexicographically if one string has millisecond precision (such as JS `.toISOString()`) and the other does not (such as GitHub API's `merged_at`), because 'Z' (ASCII 90) is lexicographically greater than '.' (ASCII 46).
Additionally, constructing a `new Date()` object inside loop callbacks (like `.filter()`) repeatedly for each element is an anti-pattern.
**Action:** Instantiation of a single reference `new Date(since)` object should be pre-calculated outside the loop, and we should use chronological comparison with `new Date(p.merged_at)` inside filters to guarantee correctness and maximize loop iteration speed.
