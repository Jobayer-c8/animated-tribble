# Bolt Performance Journal

This journal records critical, codebase-specific performance learnings to avoid mistakes or make better decisions.

## 2026-07-21 - [Lexicographical Date Comparison Pitfalls in GitHub Actions]
**Learning:** Attempting to avoid `Date` object instantiations by comparing ISO 8601 strings directly (`p.merged_at >= since`) is a dangerous premature optimization. JS `new Date().toISOString()` includes millisecond precision (e.g., `2026-07-21T12:00:00.000Z`), whereas GitHub's API response formats `merged_at` without milliseconds (e.g., `2026-07-21T12:00:00Z`). In direct lexicographical string comparison, `"Z"` (ASCII 90) is greater than `.` (ASCII 46), causing correct temporal comparisons to fail and filter out active records.
**Action:** Always favor correctness over micro-optimizations. For date comparisons where timestamp formats or precision may differ, instantiate `new Date` to ensure reliable chronological evaluation.
