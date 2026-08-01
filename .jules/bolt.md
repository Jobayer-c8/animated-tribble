# Bolt's Journal - Critical Learnings Only

## 2025-08-01 - [Parallelizing API Calls and Invariant Time Stamps]
**Learning:** In GitHub Action workflow runtimes like `actions/github-script`, making sequential async requests can result in high runtimes due to round-trip latency. Combining them using `Promise.all` improves throughput. Additionally, comparing ISO strings directly or instantiating Date objects repeatedly in loops is inefficient; parsing/creating the reference Date outside filters/loops is faster.
**Action:** Always pre-calculate invariant timestamps and parallelize independent API queries.
